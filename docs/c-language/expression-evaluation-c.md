---
title: 運算式評估 (C)
ms.date: 11/04/2016
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
ms.openlocfilehash: 37affedc0bcf3fb1423898ecf2c570794d9625c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233843"
---
# <a name="expression-evaluation-c"></a>運算式評估 (C)

涉及指派、一元遞增、一元遞減或呼叫函式的運算式可能會產生評估以外的後果 (副作用)。 到達「序列點」時，在序列點之前的全部內容 (包括任何副作用) 一定會先完成評估，然後才會對序列點之後的任何內容進行評估。

「副作用」是評估運算式所造成的變更。 每當運算式評估造成變數值變更時，就會發生副作用。 所有指派運算都有副作用。 如果函式呼叫藉由直接指派或透過指標間接指派的方式變更外部可見項目的值，則也可能有副作用。

## <a name="see-also"></a>請參閱

[運算元和運算式](../c-language/operands-and-expressions.md)
