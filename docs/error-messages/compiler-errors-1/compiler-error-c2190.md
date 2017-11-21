---
title: "編譯器錯誤 C2190 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2190
dev_langs: C++
helpviewer_keywords: C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d004d5a80e6907695f742faf6573c348662a479b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2190"></a>編譯器錯誤 C2190
第一個參數清單比第二個長  
  
 C 函式宣告以較短的參數清單的第二次。 C 不支援多載函式。  
  
 下列範例會產生 C2190:  
  
```  
// C2190.c  
// compile with: /Za /c  
void func( int, float );  
void func( int  );   // C2190, different parameter list  
void func2( int  );   // OK  
```