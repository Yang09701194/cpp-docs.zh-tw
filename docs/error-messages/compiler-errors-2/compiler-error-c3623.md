---
title: "編譯器錯誤 C3623 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3623
dev_langs: C++
helpviewer_keywords: C3623
ms.assetid: a0341b45-062a-4f67-beb9-ba74201ed1ed
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8cb9cfb2ef56d97e9414c2af0051247324e35b71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3623"></a>編譯器錯誤 C3623
'variable': Managed 或 WinRT 型別中不支援位元欄位  
  
 在 Managed 或 WinRT 類別中的變數上不允許使用位元欄位。  
  
 下列範例會產生 C3623：  
  
```  
// C3623.cpp  
// compile with: /clr  
using namespace System;  
ref class CMyClass {  
public:  
   int i : 1;   // C3623  
};  
  
int main() {  
   CMyClass^ pMyClass = gcnew CMyClass();  
   pMyClass->i = 3;  
   Console::Out->WriteLine(pMyClass->i);  
}  
```  
