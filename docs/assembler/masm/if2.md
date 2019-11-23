---
title: IF1 and IF2
ms.date: 11/21/2019
f1_keywords:
- IF2
- IF1
helpviewer_keywords:
- IF2 directive
- IF2 directive
ms.assetid: a0f75564-b51b-4e39-ad3b-f7421e7ecad6
ms.openlocfilehash: f1b5126d9294c229d773acd29af463164bb46536
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397452"
---
# <a name="if1-and-if2"></a>IF1 and IF2

**IF1** block is evaluated on first assembly pass.

**IF2** block is evaluated on every assembly pass if **OPTION:SETIF2** is **TRUE**.

## <a name="syntax"></a>語法

> **IF1;;**

> **IF2;;**

## <a name="remarks"></a>備註

See [IF](../../assembler/masm/if-masm.md) for complete syntax.

Unlike version 5.1, MASM 6.1 and above do most of its work on its first pass, then performs as many subsequent passes as necessary. In contrast, MASM 5.1 always assembles in two source passes. As a result, you may need to revise or delete some pass-dependent constructs under MASM 6.1 and above.

### <a name="two-pass-directives"></a>Two-Pass Directives

To assure compatibility, MASM 6.1 and above support 5.1 directives referring to two passes. These include **.ERR1**, **.ERR2**, **IF1**, **IF2**, **ELSEIF1**, and **ELSEIF2**. For second-pass constructs, you must specify [OPTION SETIF2](option-masm.md). Without **OPTION SETIF2**, the **IF2** and **.ERR2** directives cause an error:

```output
.ERR2 not allowed : single-pass assembler
```

MASM 6.1 and above handle first-pass constructs differently. It treats the **.ERR1** directive as **.ERR**, and the **IF1** directive as **IF**.

## <a name="see-also"></a>請參閱

[Directives reference](directives-reference.md)
