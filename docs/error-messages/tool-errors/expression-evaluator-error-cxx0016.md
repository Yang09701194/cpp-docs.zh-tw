---
title: 運算式評估工具錯誤 CXX0016 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0016
dev_langs:
- C++
helpviewer_keywords:
- CAN0016
- CXX0016
ms.assetid: af94a2ae-e835-4da6-8d2f-5c879f72eda2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e03b0567b77b1ef3f64e5cf98cbe11dab502e1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075412"
---
# <a name="expression-evaluator-error-cxx0016"></a>運算式評估工具錯誤 CXX0016

常數太大

C 運算式評估工具無法接受大於 4,294,967,295 (0FFFFFFFF 十六進位)，將不帶正負號的整數常數或浮點數的常數，其大小大於大約 1.8 e + 308。

此錯誤是與 can0016 相同。