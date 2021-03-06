---
title: void (C++)
ms.date: 11/04/2016
f1_keywords:
- void_cpp
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
ms.openlocfilehash: 2de019f908942a58b232877fcd9eebc4689d8e22
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187475"
---
# <a name="void-c"></a>void (C++)

做為函式傳回型別使用時， **void**關鍵字會指定函式不會傳回值。 當用於函式的參數清單時， **void**會指定函數不接受任何參數。 當用於指標的宣告時， **void**會指定指標為「通用」。

如果指標的類型為**void\*** ，指標可以指向未使用**const**或**volatile**關鍵字宣告的任何變數。 除非將**void\*** 指標轉換成另一個類型，否則無法將其取消引用。 **Void\*** 指標可以轉換成任何其他類型的資料指標。

**Void**指標可以指向函式，而不是中C++的類別成員。

您不能宣告**void**類型的變數。

## <a name="example"></a>範例

```cpp
// void.cpp
void vobject;   // C2182
void *pv;   // okay
int *pint; int i;
int main() {
   pv = &i;
   // Cast optional in C required in C++
   pint = (int *)pv;
}
```

## <a name="see-also"></a>另請參閱

[關鍵字](../cpp/keywords-cpp.md)<br/>
[內建類型](../cpp/fundamental-types-cpp.md)
