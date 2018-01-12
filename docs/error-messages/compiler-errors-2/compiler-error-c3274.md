---
title: "編譯器錯誤 C3274 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3274
dev_langs: C++
helpviewer_keywords: C3274
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b607445586b25b04e38c7a695cbdd78325398ba4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3274"></a>編譯器錯誤 C3274
__finally/finally 缺少對應的 try  
  
 找到缺少對應之 [的](../../cpp/try-finally-statement.md) __finally [或](../../dotnet/finally.md) finally `try`陳述式。 若要解決這個問題，請刪除 `__finally` 陳述式，或為 `try` 加入 `__finally`陳述式。  
  
 下列範例會產生 C3274：  
  
```  
// C3274.cpp  
// compile with: /clr  
// C3274 expected  
using namespace System;  
int main() {  
   try {  
      try {  
         throw gcnew ApplicationException();  
      }  
      catch(...) {  
         Console::Error->WriteLine(L"Caught an exception");  
      }  
      finally {  
         Console::WriteLine(L"In finally");  
      }  
   } finally {  
      Console::WriteLine(L"In finally");  
   }  
  
   // Uncomment the following 3 lines to resolve.  
   // try {  
   //   throw gcnew ApplicationException();  
   // }  
  
   finally {  
      Console::WriteLine(L"In finally");  
   }  
   Console::WriteLine(L"**FAIL**");  
}  
```