---
title: DLL loading exception codes (C/C++)
ms.date: 11/19/2019
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
ms.openlocfilehash: f557fe736f45f8c3f5411d076a0be18f1d1b670e
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2019
ms.locfileid: "74243857"
---
# <a name="exceptions-cc"></a>例外狀況 (C/C++)

Two exception codes can be raised when failures are encountered:

- For a **LoadLibrary** failure

- For a **GetProcAddress** failure

Here is the exception information:

```
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

The exception codes thrown are the standard VcppException(ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) and VcppException(ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND) values. The exception passes a pointer to a **DelayLoadInfo** structure in the LPDWORD value that can be retrieved by **GetExceptionInformation** in the [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) structure, ExceptionInformation[0] field.

Additionally, if the incorrect bits are set in the grAttrs field, the exception ERROR_INVALID_PARAMETER is thrown. This exception is, for all intents and purposes, fatal.

See [Structure and Constant Definitions](structure-and-constant-definitions.md) for more information.

## <a name="see-also"></a>請參閱

[錯誤處理和通知](error-handling-and-notification.md)
