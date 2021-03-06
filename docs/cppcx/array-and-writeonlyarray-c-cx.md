---
title: Array 和 WriteOnlyArray (C++/CX)
ms.date: 01/22/2017
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
ms.openlocfilehash: e050fad38d4f70c651fc0ebfddb51a33e31da6f3
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032404"
---
# <a name="array-and-writeonlyarray-ccx"></a>Array 和 WriteOnlyArray (C++/CX)

您可以在C++/CX程式中自由使用常規 C 樣式陣列或[std::array(](../standard-library/array-class-stl.md)儘管[std::vector](../standard-library/vector-class.md)通常是一個更好的選擇),但在元數據中發布的任何 API 中,必須將 C 樣式陣列或向量轉換為[Platform:array](../cppcx/platform-array-class.md)或[平臺:WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)類型,具體取決於其使用方式。 [Platform::Array](../cppcx/platform-array-class.md) 類型的效率及功能都不如 [std::vector](../standard-library/vector-class.md)，因此一般來說，您應該避免在對陣列元素執行許多作業的內部程式碼中使用此類型。

下列陣列類型可以透過 ABI 傳遞：

1. const Platform::Array^

1. Platform::Array^*

1. Platform::WriteOnlyArray

1. Platform::Array^ 的傳回值

使用這些陣列類型來實現由 Windows 執行時定義的三種陣列模式。

傳遞陣列 在調用方將陣列傳遞給方法時使用。 C++輸入參數類型為`const`[平臺:陣列](../cppcx/platform-array-class.md)\<T>。

填充陣列 在調用方傳遞要填充的方法的陣列時使用。 C++輸入參數類型為[平臺:writeonlyarray](../cppcx/platform-writeonlyarray-class.md)\<T>。

接收Array 在調用方收到方法分配的陣列時使用。 在 C++/CX 中，您可以傳回值 Array^ 傳回陣列，也可以傳回做為 Array^ 類型的 out 參數。

## <a name="passarray-pattern"></a>PassArray 模式

當用戶端程式碼將陣列傳遞至 C++ 方法，且這個方法不會修改陣列時，這個方法會以 const Array^ 形式接受陣列。 在 Windows 執行時應用程式二進位介面 (ABI) 級別,這稱為 PassArray。 下一個範例顯示如何將 JavaScript 中配置的陣列傳遞至讀取此陣列的 C++ 函式。

[!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]

下列程式碼片段示範 C++ 方法：

[!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]

## <a name="receivearray-pattern"></a>ReceiveArray 模式

在 ReceiveArray 模式中，用戶端程式碼會宣告陣列，並將它傳遞至為它配置記憶體並初始化的方法。 C++輸入參數類型是指向帽子的指標: `Array<T>^*`。 下列範例顯示如何在 JavaScript 中宣告陣列物件，並將它傳遞至 C++ 函式，此函式會配置記憶體、初始化元素，然後將它傳回至 JavaScript。 JavaScript 將配置的陣列視為傳回值，但 C++ 函式將它視為 out 參數。

[!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]

下列程式碼片段示範實作 C++ 方法的兩種方式：

[!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]

## <a name="fill-arrays"></a>填入陣列

當您想要在呼叫端配置陣列，並在被呼叫端初始化或修改它時，請使用 `WriteOnlyArray`。 下一個範例顯示如何實作使用 `WriteOnlyArray` 的 C++ 函式，以及從 JavaScript 呼叫此函式。

[!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]

下列程式碼片段示範如何實作 C++ 方法：

[!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]

## <a name="array-conversions"></a>陣列轉換

下列範例顯示如何使用 [Platform::Array](../cppcx/platform-array-class.md) 來建構其他類型的集合：

[!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]

下一個範例顯示如何從 C-Style 陣列建構 [Platform::Array](../cppcx/platform-array-class.md) ，並從公用方法中傳回它。

[!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]

## <a name="jagged-arrays"></a>不規則陣列

Windows 執行階段類型系統不支援不規則陣列的概念，因此您也就不能使用 `IVector<Platform::Array<T>>` 做為公用方法的傳回值或方法參數。 若要跨 ABI 傳遞不規則陣列或一組序列中的某個序列，請使用 `IVector<IVector<T>^>`。

## <a name="use-arrayreference-to-avoid-copying-data"></a>使用 ArrayReference 可避免複製資料

在透過 ABI 傳遞資料給 [Platform::Array](../cppcx/platform-array-class.md)，且您最終需要在 C-Style 陣列中處理資料以提升效率的某些情況下，您可以使用 [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) 避免額外的複製作業。 當您將 [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) 當做引數傳遞給採用 `Platform::Array`的參數時， `ArrayReference` 會將資料直接儲存到您指定的 C-Style 陣列中。 請注意， `ArrayReference` 不會鎖定來源資料，因此如果在呼叫完成之前修改或刪除另一個執行緒上的資料，結果會是未定義的。

下列程式碼片段示範如何將 [DataReader](/uwp/api/windows.storage.streams.datareader) 作業的結果複製到 `Platform::Array` 中 (一般模式)，以及如何接著替代 `ArrayReference` ，將資料直接複製到 C-Style 陣列中：

[!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]

## <a name="avoid-exposing-an-array-as-a-property"></a>避免將陣列公開為屬性

一般而言，您應該避免將 `Platform::Array` 類型公開為 ref 類別中的屬性，因為即使用戶端程式碼只嘗試存取單一元素，也會傳回整個陣列。 當您必須將序列容器公開為公用 ref 類別中的屬性時， [Windows::Foundation::IVector](/uwp/api/windows.foundation.collections.ivector-1) 會是較佳選擇。 在私用或內部應用程式開發介面中 (不會發行到中繼資料)，請考慮使用 Standard C++ 容器，例如 [std::vector](../standard-library/vector-class.md)。

## <a name="see-also"></a>另請參閱

[型別系統](../cppcx/type-system-c-cx.md)<br/>
[C++/CX 語言參考](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[命名空間參考](../cppcx/namespaces-reference-c-cx.md)
