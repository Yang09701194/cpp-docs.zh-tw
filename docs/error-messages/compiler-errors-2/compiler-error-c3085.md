---
title: 編譯器錯誤 C3085 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3085
dev_langs:
- C++
helpviewer_keywords:
- C3085
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57c85908d808243be8e6edce27ea22c18b4941f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3085"></a>編譯器錯誤 C3085
'constructor': 建構函式不能是 'keyword'  
  
 建構函式宣告不正確。 如需詳細資訊，請參閱 [Override Specifiers](../../windows/override-specifiers-cpp-component-extensions.md) 。  
  
## <a name="example"></a>範例  
 下列範例會產生 C3085：  
  
```  
// C3085.cpp  
// compile with: /c /clr  
ref struct S {  
   S() abstract;   // C3085  
   S(S%) abstract;   // C3085  
};  
  
ref struct T {  
   T() sealed {}   // C3085  
   T(T%) sealed {}   // C3085  
};  
```