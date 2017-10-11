---
title: "浮點常數副處理器和呼叫慣例 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6d14f7f445064316c83b31e9b4cdc421d68d7255
ms.contentlocale: zh-tw
ms.lasthandoff: 09/25/2017

---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>浮點常數副處理器和呼叫慣例
如果您要為浮點常式點副處理器撰寫組件，您必須保留浮點控制字詞並清除副處理器堆疊，除非您要傳回**float**或**double**值 （其 ST(0)) 應該傳回您的函式。  
  
## <a name="see-also"></a>另請參閱  
 [呼叫慣例](../cpp/calling-conventions.md)
