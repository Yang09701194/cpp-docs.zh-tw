---
title: "編譯器錯誤 C2289 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2289
dev_langs:
- C++
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
caps.latest.revision: 9
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
ms.openlocfilehash: 6b30911cc63d944c4b68a9711fbe8613e74c3fe8
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2289"></a>編譯器錯誤 C2289
相同類型的限定詞已經使用多次  
  
 類型宣告或定義使用類型限定詞 (`const`、 `volatile`、 `signed`、 or `unsigned`) more than once、 causing an error under ANSI compatibility (**/Za**)。  
  
 下列範例會產生 C2286：  
  
```  
// C2289.cpp  
// compile with: /Za /c  
volatile volatile int i;   // C2289  
volatile int j;   // OK  
```
