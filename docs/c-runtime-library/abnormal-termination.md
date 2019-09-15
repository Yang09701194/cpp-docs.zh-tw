---
title: _abnormal_termination
ms.date: 11/04/2016
api_name:
- _abnormal_termination
api_location:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _abnormal_termination
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
ms.openlocfilehash: b66cf0df998b4e33a9f3425fdf0f260d163f423b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944716"
---
# <a name="_abnormal_termination"></a>_abnormal_termination

指出當系統正在執行終止處理常式的內部清單時，是否輸入 [try-finally 陳述式](../cpp/try-finally-statement.md)的 `__finally` 區塊。

## <a name="syntax"></a>語法

```cpp
int   _abnormal_termination(
   );
```

## <a name="return-value"></a>傳回值

**true** 如果系統「回溯」堆疊則為 ，否則為 **false**。

## <a name="remarks"></a>備註

這是用來管理回溯例外狀況的內部函式，不是從使用者程式碼呼叫。

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|_abnormal_termination|excpt.h|

## <a name="see-also"></a>另請參閱

[try-finally 陳述式](../cpp/try-finally-statement.md)
