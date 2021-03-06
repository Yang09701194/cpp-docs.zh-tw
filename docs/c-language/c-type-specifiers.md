---
title: C 類型指定名稱
ms.date: 01/29/2018
helpviewer_keywords:
- type specifiers, C
- specifiers, type
ms.assetid: fbe13441-04c3-4829-b047-06d374adc2b6
ms.openlocfilehash: 1191cf4d2912cda535547f465fe4bfbedebe8fa2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313190"
---
# <a name="c-type-specifiers"></a>C 類型指定名稱

宣告中的類型指定名稱會定義變數或函式宣告的類型。

## <a name="syntax"></a>語法

*類型規範* &nbsp; &nbsp; &nbsp;： &nbsp; **void** &nbsp; **double** *enum-specifier* **char** &nbsp; **short** &nbsp; *typedef-name* **int** &nbsp; **float** **long** **unsigned** **signed** *struct-or-union-specifier* char short int long float double &nbsp;已簽署&nbsp;的不帶正負&nbsp;號結構或-union- &nbsp;規範 typedef-name &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;

**signed char**、**signed int**、**signed short int** 及 **signed long int** 類型，加上與其對應的 **unsigned** 及 **enum**，統稱為「整數」** 型別。 **float**、**double** 及 **long double** 類型指定名稱稱為「浮點」** 或「浮點數」** 類型。 您可以在變數或函式宣告中使用任何整數或浮點類型指定名稱。 如果未在宣告中提供 *type-specifier*，則其會當作 **int**。

選擇性關鍵字 **signed** 與 **unsigned** 可以在任何整數型別前或後 (**enum** 除外)，而且也可單獨作為類型指定名稱使用，在此情況下，這類關鍵字即分別為 **signed int** 與 **unsigned int**。 單獨使用時，會假設關鍵字 **int** 為 **signed**。 單獨使用時，關鍵字 **long** 與 **short** 即為 **long int** 與 **short int**。

列舉類型被視為基本類型。 列舉類型的類型指定名稱會在[列舉宣告](../c-language/c-enumeration-declarations.md)中討論。

關鍵字 **void** 有三個用途：指定函式傳回型別、指定不使用引數之函式的引數類型清單，以及指向未指定類型的指標。 您可以使用 **void** 類型宣告不傳回值的函式或宣告未指定類型的指標。 如需有關 **void** 單獨出現在函式名稱之後並以括弧括住時的詳細資訊，請參閱[引數](../c-language/arguments.md)。

**Microsoft 特定的**

類型檢查現在符合 ANSI 標準，這表示類型 **short** 與類型 **int** 是不同的類型。 例如，這是在舊版編譯器中接受之 Microsoft C 編譯器的重新定義。

```C
int   myfunc();
short myfunc();
```

下一個範例也會產生關於不同類型間接取值的警告：

```C
int *pi;
short *ps;

ps = pi;  /* Now generates warning */
```

Microsoft C 編譯器也會產生是否帶正負號之差異的警告。 例如：

```C
signed int *pi;
unsigned int *pu

pi = pu;  /* Now generates warning */
```

會評估類型 **void** 運算式的副作用。 您無法以任何方式使用具有 **void** 類型之運算式的 (不存在) 值，也不能將 **void** 運算式 (透過隱含或明確轉換) 轉換成 **void** 以外的任何類型。 如果您在需要 **void** 運算式的內容使用任何其他類型的運算式，則會捨棄其值。

為符合 ANSI 規格， <strong>void\* </strong>不能用來做為<strong>int\*</strong>。 只有**void** <strong>\*</strong>可以當做未指定類型的指標使用。

**結束 Microsoft 專有**

您可以使用 **typedef** 宣告建立其他類型指定名稱，如 [Typedef 宣告](../c-language/typedef-declarations.md)中所述。 如需每種類型之大小的詳細資訊，請參閱[基本類型的儲存區](../c-language/storage-of-basic-types.md)。

## <a name="see-also"></a>請參閱

[宣告和類型](../c-language/declarations-and-types.md)
