---
title: 系統呼叫
ms.date: 11/04/2016
f1_keywords:
- c.system
helpviewer_keywords:
- Windows [C++], system calls
- system calls
ms.assetid: 0255f2ec-a5a0-487e-8b09-9dad001d81ed
ms.openlocfilehash: 2d86a35718ab6c1aab941149c9707004b1532d24
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749200"
---
# <a name="system-calls"></a>系統呼叫

下列函式都是 Windows 作業系統呼叫。

## <a name="system-call-functions"></a>系統呼叫函式

|功能|使用|
|--------------|---------|
|[_findclose](../c-runtime-library/reference/findclose.md)|釋放先前尋找作業的資源|
|[_findfirst、_findfirst32、_findfirst64、_findfirsti64、_findfirst32i64、_findfirst64i32、_wfindfirst、_wfindfirst32、_wfindfirst64、_wfindfirsti64、_wfindfirst32i64、_wfindfirst64i32](../c-runtime-library/reference/findfirst-functions.md)|找出具有指定屬性的檔案|
|[_findnext、_findnext32、_findnext64、_findnexti64、_findnext32i64、_findnext64i32、_wfindnext、_wfindnext32、_wfindnexti64、_wfindnext64、_wfindnexti64](../c-runtime-library/reference/findnext-functions.md)|找出具有指定屬性的下一個檔案|

## <a name="see-also"></a>另請參閱

[依類別排序的通用 C 執行階段常式](../c-runtime-library/run-time-routines-by-category.md)<br/>
[檔案處理](../c-runtime-library/file-handling.md)<br/>
[目錄控制](../c-runtime-library/directory-control.md)<br/>
[低層級 I/O](../c-runtime-library/low-level-i-o.md)<br/>
