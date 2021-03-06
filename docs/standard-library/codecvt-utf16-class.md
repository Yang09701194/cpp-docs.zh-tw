---
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: 73177985727f4da5cf3ca4eb9e3cc3fb5976f76d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215276"
---
# <a name="codecvt_utf16"></a>codecvt_utf16

代表[地區設定](../standard-library/locale-class.md) Facet，其可在 UCS-2 或 UCS-4 編碼的寬字元以及 UTF-16LE 或 UTF-16BE 編碼的位元組資料流之間進行轉換。

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>參數

*Elem*\
寬字元項目類型。

*Maxcode*\
地區設定 Facet 的最大字元數。

*模式*\
地區設定 Facet 的設定資訊。

## <a name="remarks"></a>備註

這個類別樣板會在編碼為 UCS-2 或 UCS-4 的寬字元與編碼為 UTF-16LE 的位元組資料流程之間轉換，如果模式 & little_endian，則為，否則為 UTF-16BE。

位元組資料流應寫入二進位檔案中；如果寫入文字檔案中，則可能會損毀。

## <a name="requirements"></a>需求

標頭： \<codecvt >

命名空間: std
