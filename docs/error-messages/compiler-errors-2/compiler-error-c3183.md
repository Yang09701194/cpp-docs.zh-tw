---
title: "編譯器錯誤 C3183 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3183"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3183"
ms.assetid: dbd0f020-c739-43c9-947e-9ce21537331b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 編譯器錯誤 C3183
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

無法在 Managed 或 WinRT 類型 'type' 內部定義未命名的類別、結構或等位  
  
 內嵌在 Managed 或 WinRT 類型中的類型必須命名。  
  
 下列範例會產生 C3183：  
  
```  
// C3183a.cpp  
// compile with: /clr /c  
ref class Test  
{  
   ref class  
   {  // C3183, delete class or name it  
      int a;  
      int b;  
   };  
};  
```  
  
 下列範例會產生 C3183：  
  
```  
// C3183b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class Test  
{  
   __gc class  
   {  // C3183, delete class or name it  
      int a;  
      int b;  
   };  
};  
  
int main()  
{  
}  
```