---
title: "編譯器錯誤 C2810 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2810
dev_langs: C++
helpviewer_keywords: C2810
ms.assetid: f63e8f24-d7f6-42ac-904f-72ff49592ba6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4c1f79d519ad3ebec635525f97347b7a83aac56b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2810"></a>編譯器錯誤 C2810
'interface': 介面只可以繼承自另一個介面  
  
 [介面](../../cpp/interface.md)只能繼承自另一個介面，而且可能不是繼承自類別或結構。  
  
 下列範例會產生 C2810:  
  
```  
// C2810.cpp  
#include <unknwn.h>  
class CBase1 {  
public:  
  HRESULT mf1();  
  int  m_i;  
};  
  
[object, uuid="40719E20-EF37-11D1-978D-0000F805D73B"]  
__interface IDerived : public CBase1 {  // C2810  
// try the following line instead  
// __interface IDerived {  
   HRESULT mf2(void *a);  
};  
  
struct CBase2 {  
   HRESULT mf1(int a, char *b);  
   HRESULT mf2();  
};  
```