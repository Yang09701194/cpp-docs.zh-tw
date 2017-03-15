---
title: "編譯器警告 (層級 4) C4626 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4626"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4626"
ms.assetid: 7f822ff4-a4a3-4f17-b45b-e8b7b4659a14
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 編譯器警告 (層級 4) C4626
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'derived class'：指派運算子已隱含定義為刪除，因為基底類別指派運算子無法存取或已被刪除  
  
 指派運算子已遭刪除或無法在基底類別中存取，因此無法對衍生類別產生。  嘗試指派此類型的物件將會造成編譯器錯誤。  
  
 此警告預設為關閉。  如需詳細資訊，請參閱[預設為關閉的編譯器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)。  
  
 下列範例會產生 C4626，並示範如何修正此問題。  
  
```  
// C4626  
// compile with: /W4  
#pragma warning(default : 4626)  
class B  
{  
// public:  
   B& operator = (const B&)  
   {  
      return *this;  
   }  
};  
  
class D : public B  
{  
  
}; // C4626 - to fix, make B's copy constructor public  
  
int main()  
{  
   D m;  
   D n;  
   // m = n;   // this line will cause an error  
}  
```