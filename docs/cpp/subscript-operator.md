---
title: 註標運算子]
ms.date: 11/04/2016
f1_keywords:
- '[]'
helpviewer_keywords:
- operators [C++], subscript
- postfix operators [C++]
- '[] operator'
- subscript operator [C++], syntax
ms.assetid: 69c31494-52da-4dd0-8bbe-6ccbfd50f197
ms.openlocfilehash: 2d55c18d2c9faa1a704bea129f2551937e76133c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266890"
---
# <a name="subscript-operator-"></a>註標運算子]

## <a name="syntax"></a>語法

```
postfix-expression [ expression ]
```

## <a name="remarks"></a>備註

（這也是主要運算式） 後面接著註標運算子中後, 置運算式 **[]**，指定陣列索引。

如需在 managed 陣列的詳細資訊C++/CLI，請參閱[陣列](../extensions/arrays-cpp-component-extensions.md)。

通常所代表的值*後置運算式*是指標值，例如陣列識別項，並*運算式*是整數值 （包括列舉型別）。 不過，在語法上需要的是其中一個指標類型的運算式，另一個則是整數類型。 因此，整數值可以在*後置運算式*位置，而指標值可以在括號括住*運算式*或註標位置。 請考慮下列程式碼片段：

```cpp
int nArray[5] = { 0, 1, 2, 3, 4 };
cout << nArray[2] << endl;            // prints "2"
cout << 2[nArray] << endl;            // prints "2"
```

在上述範例中，運算式 `nArray[2]` 與 `2[nArray]` 相同。 原因在於註標運算式的結果`e1[e2]`所指定：

`*((e2) + (e1))`

運算式所產生的位址不是*e2*位元組從位址*e1*。 相反地，位址會產生陣列中的下一個物件進行縮放*e2*。 例如：

```cpp
double aDbl[2];
```

地址`aDb[0]`及`aDb[1]`為 8 個位元組的位置 — 型別的物件的大小**double**。 此調整根據物件類型會自動進行C++語言和定義於[加法類運算子](../cpp/additive-operators-plus-and.md)討論加法和減法的指標類型的運算元。

註標運算式也可以擁有多個註標，如下所示：

*expression1* **[** *expression2* **] [** *expression3* **]** ...

註標運算式的關聯是由左至右。 最左邊的下標運算式 *expression1* **[** *expression2* **]** 會最先評估。 *expression1* 和 *expression2* 相加所產生的位址會形成指標運算式，然後 *expression3* 會加入這個指標運算式形成新的指標運算式，依此類推，直到加入最後一個註標運算式為止。 間接取值運算子 (<strong>\*</strong>) 之後，會套用最後一個註標的運算式評估時，除非最後一個指標值定址為陣列類型。

具有多個註標的運算式會參考多維陣列的元素。 所謂的多維陣列是指其中所包含的元素也是一種陣列。 例如，三維陣列的第一個元素是具有兩個維度的陣列。 下列範例會宣告和初始化一個簡單的二維字元陣列：

```cpp
// expre_Subscript_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
#define MAX_ROWS 2
#define MAX_COLS 2

int main() {
  char c[ MAX_ROWS ][ MAX_COLS ] = { { 'a', 'b' }, { 'c', 'd' } };
  for ( int i = 0; i < MAX_ROWS; i++ )
     for ( int j = 0; j < MAX_COLS; j++ )
        cout << c[ i ][ j ] << endl;
}
```

## <a name="positive-and-negative-subscripts"></a>正數和負數註標

陣列的第一個元素是元素 0。 範圍C++陣列是從*陣列*[0] 以*陣列*[*大小*-1]。 不過，C++ 支援正註標和負註標。 負註標必須在陣列界限內，如果不在界限內，則無法預測結果。 下列程式碼顯示正的和負的陣列註標：

```cpp
#include <iostream>
using namespace std;

int main() {
    int intArray[1024];
    for (int i = 0, j = 0; i < 1024; i++)
    {
        intArray[i] = j++;
    }

    cout << intArray[512] << endl;   // 512

    cout << 257[intArray] << endl;   // 257

    int *midArray = &intArray[512];  // pointer to the middle of the array

    cout << midArray[-256] << endl;  // 256

    cout << intArray[-256] << endl;  // unpredictable, may crash
}
```

在最後一行中的負註標可以產生執行階段錯誤，因為它所指向的地址 256 **int**中的位置較低的記憶體比原始伺服器的陣列。 指標`midArray`初始化為的中間`intArray`; 您可因此 （但濫用） 在其上使用這兩個正和負的陣列索引。 陣列註標錯誤不會產生編譯時間錯誤，但是會產生無法預期的結果。

註標運算子可以交替。 因此，運算式*陣列*[*index*] 和*索引*[*陣列*] 並保證只要註標是對等運算子未多載 (請參閱[多載運算子](../cpp/operator-overloading.md))。 第一種形式是最常用的程式撰寫作法，但兩種都可以運作。

## <a name="see-also"></a>另請參閱

[後置運算式](../cpp/postfix-expressions.md)<br/>
[C++ 內建運算子、優先順序和順序關聯性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[陣列](../cpp/arrays-cpp.md)<br/>
[一維陣列](../c-language/one-dimensional-arrays.md)<br/>
[多維陣列](../c-language/multidimensional-arrays-c.md)<br/>
