---
title: C 常數運算式
ms.date: 06/14/2018
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
ms.openlocfilehash: f6984c47ef8acde462a8e92e01b72ef26a61eddc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325737"
---
# <a name="c-constant-expressions"></a>C 常數運算式

常數運算式會在編譯時期評估，而不是在執行階段評估，而且可用於可以使用常數的任何位置。 常數運算式必須評估為常數，並且必須在該類型可顯示值的範圍內。 常數運算式的運算元可以是整數常數、字元常數、浮點常數、列舉常數、類型轉換、**sizeof** 運算式與其他常數運算式。

## <a name="syntax"></a>語法

*常數運算式*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*條件運算式*

*條件運算式*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*logical-OR-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*邏輯 OR 運算式* **？** *expression* **：** *條件運算式*

*expression*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*指派-運算式*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*運算式* **，** *指派運算式*

*assignment-expression*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*條件運算式*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unary-expression* *assignment-operator* *assignment-expression*

*assignment-operator*：下列其中一個<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**=****&#42;** **/=** **%=** = **+=** **-=** **&#124;** = ** \< \< ** **>>=** **&=** **^=**

結構宣告子、列舉程式、直接宣告子、直接抽象宣告子和標記陳述式包含 *constant-expression* 非終端項。

必須使用整數常數運算式指定結構的位元欄位成員、列舉常數的值、陣列的大小或 **case** 常數的值。

前置處理器指示詞中所使用的常數運算式必須遵守其他限制。 因此，這些運算式稱為「受限制的常數運算式」。 受限制的常數運算式不能包含 **sizeof** 運算式、列舉常數、任何類型的類型轉換，或浮點類型常數。 不過，此類運算式可以包含已定義的特殊常數運算式 ** (** _identifier_ **)**.

## <a name="see-also"></a>請參閱

- [運算元和運算式](../c-language/operands-and-expressions.md)
