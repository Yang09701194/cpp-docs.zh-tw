---
title: 編譯器警告 (層級 2) C4412
ms.date: 11/04/2016
f1_keywords:
- C4412
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
ms.openlocfilehash: 601b99eec4625e9b598ece4cbb74d0039ad04bf0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161785"
---
# <a name="compiler-warning-level-2-c4412"></a>編譯器警告 (層級 2) C4412

> '*function*'：函數簽名碼包含類型 '*type*';C++物件在純程式碼與混合或原生之間傳遞不安全。

## <a name="remarks"></a>備註

**/Clr： pure**編譯器選項在 Visual Studio 2015 中已被取代，在 Visual Studio 2017 中不支援。 如果您的程式碼必須是純虛擬，建議您將它移植到C#。

編譯器偵測到可能導致執行階段錯誤的潛在不安全情況：從 **/clr： pure**編譯模組對透過 dllimport 匯入的函式進行呼叫，而且函數簽章包含不安全的類型。 如果類型包含成員函式，或具有不安全類型的資料成員或不安全類型的間接取值，則該類型不安全。

這是不安全的，因為純粹和機器碼（或混合原生和 managed）之間的預設呼叫慣例有差異。 將函式匯入（透過 `dllimport`）函式至 **/clr： pure**編譯模組時，請確定簽章中每個類型的宣告與匯出函式的編譯模組中的宣告相同（特別小心，隱含呼叫慣例的差異）。

虛擬成員函式特別容易提供非預期的結果。  不過，即使是非虛擬函式，也應該進行測試，以確保您得到正確的結果。 如果您確定得到正確的結果，可以忽略此警告。

C4412 預設為關閉。 如需詳細資訊，請參閱[預設為關閉的編譯器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)和[dllexport、dllimport](../../cpp/dllexport-dllimport.md) 。

若要解決這個警告，請移除類型中的所有函式。

## <a name="example"></a>範例

下列範例會產生 C4412。

```cpp
// C4412.cpp
// compile with: /c /W2 /clr:pure
#pragma warning (default : 4412)

struct Unsafe {
   virtual void __cdecl Test();
};

struct Safe {
   int i;
};

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   Unsafe *pUnsafe = func();   // C4412
   // pUnsafe->Test();

   Safe *pSafe = func2();   // OK
}
```

## <a name="example"></a>範例

下列範例是宣告兩種類型的標頭檔。 `Unsafe` 類型是不安全的，因為它有成員函式。

```cpp
// C4412.h
struct Unsafe {
   // will be __clrcall if #included in pure compilation
   // defaults to __cdecl in native or mixed mode compilation
   virtual void Test(int * pi);

   // try the following line instead
   // virtual void __cdecl Test(int * pi);
};

struct Safe {
   int i;
};
```

## <a name="example"></a>範例

這個範例會使用標頭檔中所定義的類型來匯出函式。

```cpp
// C4412_2.cpp
// compile with: /LD
#include "C4412.h"

void Unsafe::Test(int * pi) {
   *pi++;
}

__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }
```

## <a name="example"></a>範例

**/Clr： pure**編譯中的預設呼叫慣例與原生編譯不同。  當包含 C4412 時，`Test` 預設為 `__clrcall`。 如果您編譯並執行此程式（不使用 **/c**），程式將會擲回例外狀況。

下列範例會產生 C4412。

```cpp
// C4412_3.cpp
// compile with: /W2 /clr:pure /c /link C4412_2.lib
#pragma warning (default : 4412)
#include "C4412.h"

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   int n = 7;
   Unsafe *pUnsafe = func();   // C4412
   pUnsafe->Test(&n);

   Safe *pSafe = func2();   // OK
}
```
