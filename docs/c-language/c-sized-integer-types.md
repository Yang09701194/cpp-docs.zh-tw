---
title: C 大小的整數類型
ms.date: 11/04/2016
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
ms.openlocfilehash: 136065466d3adb4017cf18f2baf8c3387ffbd035
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313294"
---
# <a name="c-sized-integer-types"></a>C 大小的整數類型

**Microsoft 特定的**

Microsoft C 的功能支援可調整大小的整數類型。 您可以使用 __int*n* 類型規範來宣告 8、16、32 或 64 位元的整數變數，其中 *n* 為整數變數的大小 (以位元為單位)。 *n* 的值可以是 8、16、32 或 64。 下列範例宣告了四種可調整大小整數類型的變數：

```
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

前三類可調整大小的整數與具有相同大小的 ANSI 類型同義，且當撰寫可移植程式碼的行為模式在多個平台上完全相同時，這也會很有用。 請注意，__int8 資料類型與 char 類型同義， \__int16 與 short 類型同義，而\__int32 是與 int 類型同義。\__Int64 類型沒有對等的 ANSI 對應項。

**結束 Microsoft 專有**

## <a name="see-also"></a>請參閱

[基本類型的儲存空間](../c-language/storage-of-basic-types.md)
