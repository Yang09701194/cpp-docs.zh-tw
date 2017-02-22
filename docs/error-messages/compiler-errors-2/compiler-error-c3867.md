---
title: "編譯器錯誤 C3867 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3867"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3867"
ms.assetid: bc5de03f-e01a-4407-88c3-2c63f0016a1e
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# 編譯器錯誤 C3867
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'func': 函式呼叫遺漏引數清單，請用 '&func' 建立成員的指標  
  
 您嘗試取得成員函式的位址，而未使用其類別名稱和傳址運算子來限定成員函式。  
  
 針對 Visual C\+\+ 2005 所進行的編譯器一致性工作，也可能會導致這個錯誤：增強的指標對成員一致性。  在 Visual C\+\+ 2005 之前編譯的程式碼現在會產生 C3867。  
  
## 範例  
 使用誤導的建議解決方法，即可從編譯器發出 C3867。  若可能，請使用最新衍生的類別。  
  
 下列範例會產生 C3867，並示範如何修正此問題。  
  
```  
// C3867_1.cpp  
// compile with: /c  
struct Base {   
protected:   
   void Test() {}  
};  
  
class Derived : public Base {   
   virtual void Bar();  
};  
  
void Derived::Bar() {  
   void (Base::*p1)() = Test;   // C3867  
   &Derived::Test;   // OK  
}  
```  
  
## 範例  
 下列範例會產生 C3867，並示範如何修正此問題。  
  
```  
// C3867_2.cpp  
#include<stdio.h>  
  
struct S {  
   char *func() {  
      return "message";  
   }  
};  
  
class X {  
public:  
   void f() {}  
};  
  
int main() {  
   X::f;   // C3867  
  
   // OK  
   X * myX = new X;  
   myX->f();  
  
   S s;  
   printf_s("test %s", s.func);   // C3867  
   printf_s("test %s", s.func());   // OK  
}  
```  
  
## 範例  
 下列範例會產生 C3867，並示範如何修正此問題。  
  
```  
// C3867_3.cpp  
class X {  
public:  
   void mf(){}  
};  
  
int main() {  
   void (X::*pmf)() = X::mf;   // C3867  
  
   // try the following line instead  
   void (X::*pmf2)() = &X::mf;  
}  
```  
  
## 範例  
 下列範例會產生 C3867。  
  
```  
// C3867_4.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b1;  
      b1.p = f;   // C3867  
   }  
};  
```  
  
## 範例  
 下列範例會產生 C3867。  
  
```  
// C3867_5.cpp  
// compile with: /EHsc  
#include <iostream>  
  
class Testpm {  
public:  
   void m_func1() {  
      std::cout << m_num << "\tm_func1\n";   
    }  
  
   int m_num;  
   typedef void (Testpm::*pmfn1)();  
   void func(Testpm* p);  
};  
  
void Testpm::func(Testpm* p) {  
   pmfn1 s = m_func1;   // C3867  
   pmfn1 s2 = &Testpm::m_func1;   // OK  
   (p->*s2)();  
}  
  
int main() {  
   Testpm *pTestpm = new Testpm;  
   pTestpm->m_num = 10;  
  
   pTestpm->func(pTestpm);  
}  
```