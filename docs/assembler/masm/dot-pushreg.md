---
title: .PUSHREG
ms.date: 08/30/2018
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: 2190bd05667de82dada34a63f11647c653f97247
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398028"
---
# <a name="pushreg"></a>.PUSHREG

Generates a `UWOP_PUSH_NONVOL` unwind code entry for the specified register number using the current offset in the prologue.

## <a name="syntax"></a>語法

> .PUSHREG register

## <a name="remarks"></a>備註

**.PUSHREG** allows ml64.exe users to specify how a frame function unwinds, and is only allowed within the prologue, which extends from the [PROC](../../assembler/masm/proc.md) **FRAME** declaration to the [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) directive. These directives do not generate code; they only generate `.xdata` and `.pdata`. **.PUSHREG** should be preceded by instructions that actually implement the actions to be unwound. It is a good practice to wrap both the unwind directives and the code they are meant to unwind in a macro to ensure agreement.

For more information, see [MASM for x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="sample"></a>範例

### <a name="description"></a>描述

The following sample shows how to push non-volatile registers.

### <a name="code"></a>程式碼

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

## <a name="see-also"></a>請參閱

[Directives reference](directives-reference.md)
