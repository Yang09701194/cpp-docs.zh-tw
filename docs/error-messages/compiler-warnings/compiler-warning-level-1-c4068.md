---
title: "編譯器警告 （層級 1） C4068 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4068
dev_langs:
- C++
helpviewer_keywords:
- C4068
ms.assetid: 96a7397a-4eab-44ab-b3bb-36747503f7e5
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 6583ed19889de77ee6edd784662cad9bf60f9643
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4068"></a>編譯器警告 (層級 1) C4068
未知的 pragma  
  
 編譯器已忽略無法辨識[pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)。 請確認您使用的編譯器允許 **pragma** 。 下列範例會產生 C4068：  
  
```  
// C4068.cpp  
// compile with: /W1  
#pragma NotAValidPragmaName   // C4068, use valid name to resolve  
int main()  
{  
}  
```
