---
title: SEGMENT
ms.date: 08/30/2018
f1_keywords:
- SEGMENT
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
ms.openlocfilehash: b7344d9cb685e0212748d7835e19f398f14979e7
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/22/2019
ms.locfileid: "74393732"
---
# <a name="segment"></a>SEGMENT

Defines a program segment called *name* having segment attributes

## <a name="syntax"></a>語法

> *name* **SEGMENT** ⟦**READONLY**⟧ ⟦*align*⟧ ⟦*combine*⟧ ⟦*use*⟧ ⟦*characteristics*⟧ **ALIAS(** _string_ **)** ⟦ __'__ *class* __'__ ⟧\
> *statements*\
> *name* **ENDS**

#### <a name="parameters"></a>參數

*align*<br/>
The range of memory addresses from which a starting address for the segment can be selected. The alignment type can be any one of the following:

|Align Type|Starting Address|
|----------------|----------------------|
|**BYTE**|Next available byte address.|
|**WORD**|Next available word address (2 bytes per word).|
|**DWORD**|Next available double word address (4 bytes per double word).|
|**PARA**|Next available paragraph address (16 bytes per paragraph).|
|**PAGE**|Next available page address (256 bytes per page).|
|**ALIGN**(*n*)|Next available *n*th byte address. See Remarks section for more information.|

If this parameter is not specified, **PARA** is used by default.

*combine*\
**PUBLIC**, **STACK**, **COMMON**, **MEMORY**, **AT**<em>address</em>, **PRIVATE**

*use*\
**USE16**, **USE32**, **FLAT**

*characteristics*\
**INFO**, **READ**, **WRITE**, **EXECUTE**, **SHARED**, **NOPAGE**, **NOCACHE**, and **DISCARD**

These are supported for COFF only and correspond to the COFF section characteristics of similar name (for example, **SHARED** corresponds to IMAGE_SCN_MEM_SHARED). READ sets the IMAGE_SCN_MEM_READ flag. The obsolete READONLY flag caused the section to clear the IMG_SCN_MEM_WRITE flag. If any *characteristics* are set, the default characteristics are not used and only the programmer-specified flags are in effect.

_string_\
This string is used as the section name in the emitted COFF object.  Creates multiple sections with the same external name, with distinct MASM segment names.

Not supported with **/omf**.

*class*\
Designates how segments should be combined and ordered in the assembled file. Typical values are, `'DATA'`, `'CODE'`, `'CONST'` and `'STACK'`

## <a name="remarks"></a>備註

For `ALIGN(n)`, *n* may be any power of 2 from 1 to 8192; not supported with **/omf**.

## <a name="see-also"></a>請參閱

[Directives reference](directives-reference.md)
