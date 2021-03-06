---
title: 錯誤處理 (CRT)
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
ms.openlocfilehash: d38aaf76a4901b12290782957db90049d815d278
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443316"
---
# <a name="error-handling-crt"></a>錯誤處理 (CRT)

您可以使用這些常式來處理程式錯誤。

## <a name="error-handling-routines"></a>錯誤處理常式

|常式|使用|
|-------------|---------|
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 巨集|測試程式設計邏輯錯誤。適用於發行和偵錯版本的執行階段程式庫。|
|[_ASSERT、_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 巨集|類似於**判斷提示**，但僅適用於偵錯版本的執行階段程式庫。|
|[clearerr](../c-runtime-library/reference/clearerr.md)|重設錯誤指標。 呼叫 **rewind** 或關閉資料流也會重設錯誤指標。|
|[_eof](../c-runtime-library/reference/eof.md)|檢查低層級 I/O 的檔案結尾。|
|[feof](../c-runtime-library/reference/feof.md)|測試檔案結尾。 當 **_read** 傳回 0 時，也表示檔案結尾。|
|[ferror](../c-runtime-library/reference/ferror.md)|測試資料流 I/O 錯誤。|
|[_RPT、_RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) 巨集|產生類似於 **printf** 的報表，但僅適用於偵錯版本的執行階段程式庫。|
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|修改 **__error_mode** 來判斷非預設位置，其中 C 執行階段寫入可能會結束程式之錯誤的錯誤訊息。|
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|設定純虛擬函式呼叫的處理常式。|

## <a name="see-also"></a>另請參閱

- [依類別排序的通用 C 執行階段常式](../c-runtime-library/run-time-routines-by-category.md)
