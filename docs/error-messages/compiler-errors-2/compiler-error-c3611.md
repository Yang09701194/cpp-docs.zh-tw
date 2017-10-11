---
title: "編譯器錯誤 C3611 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3611
dev_langs:
- C++
helpviewer_keywords:
- C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cfd4d0cb336f540387ad8f135c02c512a5282e26
ms.contentlocale: zh-tw
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3611"></a>編譯器錯誤 C3611
'function': 密封函式不能有純規範  
  
 密封函式宣告不正確。  如需詳細資訊，請參閱[密封](../../windows/sealed-cpp-component-extensions.md)。  
  
## <a name="example"></a>範例  
 下列範例會產生 C3611。  
  
```  
// C3611.cpp  
// compile with: /clr /c  
  
ref struct V {  
   virtual void Test() sealed = 0;   // C3611  
   virtual void Test2() sealed;   // OK  
   virtual void Test3() = 0;   // OK  
};  
```
