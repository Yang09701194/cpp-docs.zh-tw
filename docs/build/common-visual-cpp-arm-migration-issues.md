---
title: Visual C++ ARM 移轉時常見的問題
ms.date: 05/06/2019
ms.assetid: 0f4c434e-0679-4331-ba0a-cc15dd435a46
ms.openlocfilehash: 2c29b4ffa5344b309622314970ce52c47a0ebd05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328802"
---
# <a name="common-visual-c-arm-migration-issues"></a>Visual C++ ARM 移轉時常見的問題

使用 Microsoft c + + 編譯器（MSVC）時，相同的 c + + 原始程式碼在 ARM 架構上可能會產生不同的結果，而不是在 x86 或 x64 架構上。

## <a name="sources-of-migration-issues"></a>遷移問題的來源

當您從 x86 或 x64 架構將程式碼遷移至 ARM 架構時，可能會遇到許多問題，與可能叫用未定義、執行定義或未指定行為的原始程式碼結構有關。

*未定義的行為*是 c + + 標準未定義的行為，而這是由沒有合理結果的作業所造成：例如，將浮點值轉換為不帶正負號的整數，或將值設為負數或超過其升級類型中的位數。

*實作為定義行為*是 c + + 標準要求編譯器廠商定義和記錄的行為。 程式可以安全地依賴執行定義的行為，即使這樣做可能無法移植。 實作為定義行為的範例包括內建資料類型的大小及其對齊需求。 可能受到實作為定義行為影響的作業範例，就是存取變數引數清單。

*未指定的行為*是 c + + 標準有意不具決定性的行為。 雖然行為會被視為不具決定性，但特定的未指定行為調用是由編譯器執行所決定。 不過，編譯器廠商不需要預先確定結果，或保證可比較的調用之間的一致行為，而且不需要檔。 未指定行為的範例是評估子運算式（其中包含函式呼叫的引數）的順序。

其他遷移問題的特性可能是 ARM 和 x86 或 x64 架構之間的硬體差異，與 c + + 標準互動的方式不同。 例如，x86 和 x64 架構的強式記憶體模型會提供`volatile`一些額外的屬性，這些屬性已經用來加速過去的特定執行緒間通訊類型。 但是 ARM 架構的弱式記憶體模型不支援這種用法，c + + 標準也不會要求它。

> [!IMPORTANT]
> 雖然`volatile`取得一些可用來在 x86 和 x64 上執行有限形式之執行緒間通訊的屬性，但這些額外的屬性並不足以在一般情況下執行執行緒間通訊。 C + + 標準建議您改用適當的同步處理原始物件來執行這類通訊。

由於不同的平臺可能會以不同的方式表達這類行為，因此如果在平臺之間移植軟體，可能會很棘手，而且如果相依于特定平臺的行為，則不容易發生錯誤。 雖然可能會觀察到這類行為，而且可能會變穩定，但依賴它們至少是不可移植的，而且在未定義或未指定的行為情況下，也是錯誤。 即使本檔中提及的行為不應依賴，而且未來的編譯器或 CPU 執行可能會改變。

## <a name="example-migration-issues"></a>範例遷移問題

本檔的其餘部分將說明這些 c + + 語言元素的不同行為如何在不同的平臺上產生不同的結果。

### <a name="conversion-of-floating-point-to-unsigned-integer"></a>浮點到不帶正負號整數的轉換

在 ARM 架構上，如果浮點值超出整數可以代表的範圍，則將浮點值轉換為32位整數會使其達到最接近的值。 在 x86 和 x64 架構上，如果整數不帶正負號，轉換就會換行，如果整數已簽署，則會設定為-2147483648。 這些架構都不會直接支援將浮點值轉換成較小的整數類型;相反地，轉換會執行為32位，而結果會被截斷為較小的大小。

就 ARM 架構而言，飽和度和截斷的組合表示轉換成不帶正負號的型別，會在最少使用32位整數時，正確地使不帶正負號的型別變得更好，但針對大於較小類型的值，會產生截斷的結果，但太小，無法使整個32位整數飽和。 轉換也適用于32位帶正負號的整數，但是截斷飽和的帶正負號的整數會產生-1 代表有效的值，而0則表示負面飽和的值。 轉換成較小帶正負號的整數會產生無法預測的截斷結果。

針對 x86 和 x64 架構，不帶正負號整數轉換的換行行為的組合以及溢位的帶正負號整數轉換的明確評估會連同截斷，如果太大，則會讓大部分移位的結果變得無法預測。

這些平臺也會因其處理 NaN （非數位）與整數類型的轉換方式而有所不同。 在 ARM 上，NaN 會轉換成 0x00000000;在 x86 和 x64 上，它會轉換成0x80000000。

只有在您知道值是在要轉換成的整數類型範圍內時，才能依賴浮點轉換。

### <a name="shift-operator---behavior"></a>移位運算子（\< \< >>）行為

在 ARM 架構上，可以在模式開始重複之前，將值向左或向右移動到255位。 在 x86 和 x64 架構上，除非模式的來源是64位變數，否則會在32的每個倍數重複模式。在這種情況下，模式會在 x64 上的每個64，以及 x86 上每多個256（採用軟體實行的地方）重複執行。 例如，針對32位變數，其值為1，由32個位置左移，在 ARM 上的結果為0，在 x86 上的結果為1，而在 x64 上，結果也是1。 不過，如果值的來源是64位變數，則在所有三個平臺上的結果都是4294967296，而此值將不會「換行」，直到在 x64 上移動64位置或 ARM 和 x86 上的256位置為止。

因為移位運算的結果超過來源類型中的位數目，所以編譯器在所有情況下都不需要有一致的行為。 例如，如果在編譯時期都知道移位的兩個運算元，編譯器可能會使用內部常式來預先計算排班的結果，然後將結果取代為移位作業，以優化程式。 如果移位量太大或為負，則內部常式的結果可能會與 CPU 所執行的相同移位運算式的結果不同。

### <a name="variable-arguments-varargs-behavior"></a>變數引數（varargs）行為

在 ARM 架構上，從堆疊上傳遞的可變引數清單中的參數可能會對齊。 例如，64位參數在64位界限上對齊。 在 x86 和 x64 上，在堆疊上傳遞的引數不會受到對齊和緊密封裝的規範。 這項差異可能會導致 variadic `printf`函式，例如讀取在 ARM 上做為填補的記憶體位址。如果變數引數清單的預期配置不完全相符，即使它可能適用于 x86 或 x64 架構上部分值的子集。 請思考此範例：

```C
// notice that a 64-bit integer is passed to the function, but '%d' is used to read it.
// on x86 and x64 this may work for small values because %d will "parse" the low-32 bits of the argument.
// on ARM the calling convention will align the 64-bit value and the code will print a random value
printf("%d\n", 1LL);
```

在此情況下，您可以確保使用正確的格式規格，以便考慮引數的對齊方式，藉以修正 bug。 這段程式碼是正確的：

```C
// CORRECT: use %I64d for 64-bit integers
printf("%I64d\n", 1LL);
```

### <a name="argument-evaluation-order"></a>引數評估順序

因為 ARM、x86 和 x64 處理器的差異很大，所以它們可以呈現不同的需求給編譯器的執行，也會有不同的優化機會。 因此，與其他因素（例如呼叫慣例和優化設定）搭配使用時，編譯器可能會在不同的架構上以不同的順序評估函式引數，或其他因素變更時。 這可能會導致依賴特定評估順序的應用程式行為意外變更。

當函式的引數有副作用會影響相同呼叫中函數的其他引數時，可能會發生這種錯誤。 通常這種相依性很容易避免，但有時可能會因為難以辨識的相依性或由運算子多載而遮蔽。 請考慮下列程式碼範例：

```cpp
handle memory_handle;

memory_handle->acquire(*p);
```

這會顯示妥善定義的，但`->`如果`*`和是多載運算子，則此程式碼會轉譯成類似下面的內容：

```cpp
Handle::acquire(operator->(memory_handle), operator*(p));
```

而且，如果和`operator->(memory_handle)` `operator*(p)`之間有相依性，則程式碼可能會依賴特定的評估順序，即使原始程式碼看起來就像沒有可能的相依性。

### <a name="volatile-keyword-default-behavior"></a>volatile 關鍵字的預設行為

MSVC 編譯器支援兩種不同的`volatile`儲存限定詞解讀，您可以使用編譯器參數來指定。 [/Volatile： ms](reference/volatile-volatile-keyword-interpretation.md)參數會選取可確保強式排序的 Microsoft 擴充 volatile 語義，因為這是傳統的 x86 和 x64 案例，因為這些架構上的強式記憶體模型。 [/Volatile： iso](reference/volatile-volatile-keyword-interpretation.md)參數會選取嚴格的 c + + 標準 volatile 語義，而不保證強式排序。

在 ARM 架構上，預設值為 **/volatile： iso** ，因為 arm 處理器具有弱式排序的記憶體模型，而且因為 arm 軟體沒有依賴 **/volatile： ms**的擴充語義的舊版，而且通常不需要與執行的軟體進行介面的互動。 不過，它有時候也很方便，甚至是編譯 ARM 程式以使用擴充的語義時也是必要的。 例如，將程式移植到使用 ISO c + + 的語義可能會太昂貴，或驅動程式軟體可能必須遵守傳統的語義，才能正常運作。 在這些情況下，您可以使用 **/volatile： ms**參數;不過，若要在 ARM 目標上重新建立傳統的 volatile 語義，編譯器必須在每次讀取或寫入`volatile`變數時插入記憶體屏障，以強制執行強式排序，這對效能可能會有負面影響。

在 x86 和 x64 架構上，預設值為 **/volatile： ms** ，因為已使用 MSVC 為這些架構建立的大部分軟體都依賴它們。 當您編譯 x86 和 x64 程式時，您可以指定 **/volatile： iso**參數來協助避免不必要的依賴傳統 volatile 語義，並提升可攜性。

## <a name="see-also"></a>請參閱

[針對 ARM 處理器設定 Visual C++](configuring-programs-for-arm-processors-visual-cpp.md)
