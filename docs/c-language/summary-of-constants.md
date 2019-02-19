---
title: 常數摘要
ms.date: 11/04/2016
helpviewer_keywords:
- constants, C
ms.assetid: 4158234c-e189-4e25-970f-52a04bc6380a
ms.openlocfilehash: f927d977d818bed28c5fd7392f7933cd1a63ced3
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2019
ms.locfileid: "56150021"
---
# <a name="summary-of-constants"></a>常數摘要

*constant*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*floating-point-constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*integer-constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enumeration-constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*character-constant*

*floating-point-constant*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*fractional-constant* *exponent-part*<sub>opt</sub> *floating-suffix*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence* *exponent-part* *floating-suffix*<sub>opt</sub>

*fractional-constant*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence*<sub>opt</sub> **.** *digit-sequence*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence*  **.**

*exponent-part*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**e** *sign*<sub>opt</sub> *digit-sequence*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**E** *sign*<sub>opt</sub> *digit-sequence*

*sign*：下列其中一個<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**+ -**

*digit-sequence*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence* *digit*

*floating-suffix*：下列其中一個<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**f l F L**

*integer-constant*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*decimal-constant* *integer-suffix*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*binary-constant* *integer-suffix*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*octal-constant* *integer-suffix*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*hexadecimal-constant* *integer-suffix*<sub>opt</sub>

*decimal-constant*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*nonzero-digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*decimal-constant* *digit*

*binary-constant*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0b** *binary-digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0B** *binary-digit*

*octal-constant*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*octal-constant* *octal-digit*

*hexadecimal-constant*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0x**  *hexadecimal-digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0X**  *hexadecimal-digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*hexadecimal-constant* *hexadecimal-digit*

*nonzero-digit*：下列其中一個<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**1 2 3 4 5 6 7 8 9**

*octal-digit*：下列其中一個<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7**

*hexadecimal-digit*：下列其中一個<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**a b c d e f**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**A B C D E F**

*unsigned-suffix*：下列其中一個<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**u U**

*long-suffix*：下列其中一個<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**l L**

*character-constant*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**'** *c-char-sequence* **'**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**L'** *c-char-sequence* **'**

*integer-suffix*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unsigned-suffix* *long-suffix*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*long-suffix* *unsigned-suffix*<sub>opt</sub>

*c-char-sequence*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*c-char*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*c-char-sequence* *c-char*

*c-char*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;來源字元集的所有成員，但不包括單引號 (**'**)、反斜線 (**\\**) 或新行字元 escape-sequence

*escape-sequence*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*simple-escape-sequence*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*octal-escape-sequence*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*hexadecimal-escape-sequence*

*simple-escape-sequence*：下列其中一個<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**\a \b \f \n \r \t \v**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**\\' \\" \\\ \\?**

*octal-escape-sequence*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**\\** *octal-digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**\\** *octal-digit* *octal-digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**\\** *octal-digit* *octal-digit* *octal-digit*

*hexadecimal-escape-sequence*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**\x** *hexadecimal-digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*hexadecimal-escape-sequence* *hexadecimal-digit*

## <a name="see-also"></a>另請參閱

[語彙文法](../c-language/lexical-grammar.md)<br/>
