---
title: "如何：使用 for each 反覆查看陣列 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "陣列 [C++], 使用 for each 逐一查看"
ms.assetid: ddc88ce2-69e1-44fc-af84-5b6f62fcb9e3
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 如何：使用 for each 反覆查看陣列
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

本主題說明如何使用在陣列中的不同型別的 [for each、in](../dotnet/for-each-in.md) 關鍵字。  
  
## 範例  
 這個範例顯示如何使用在陣列的 `for each` 參考型別。請注意，如果多維度陣列的任何維度長度為零， `for each` 迴圈會逐一查看陣列。  
  
```  
// for_each_arrays.cpp  
// compile with: /clr  
using namespace System;  
ref struct MyClass {  
   void Test() { Console::WriteLine("in MyClass"); }  
};  
  
ref struct MyClass2 {  
   void Test() { Console::WriteLine("in MyClass2"); }  
};  
  
int main() {  
   array<MyClass ^> ^ MyArray = gcnew array<MyClass ^>(2);  
  
   int i = 0;  
   for each ( MyClass ^ c in MyArray ) {  
      Console::Write("{0} = ", i++);  
      c -> Test();  
   }  
  
   Console::WriteLine();  
  
   array< MyClass2 ^, 2 > ^ MyArray2 = gcnew array< MyClass2 ^, 2 >(2, 2);  
   i = 0;  
   for each ( MyClass2 ^ c in MyArray2 ) {  
      Console::Write("{0} = ", i++);  
      c -> Test();  
   }  
  
   array< MyClass2 ^, 2 > ^ MyArray3 = gcnew array< MyClass2 ^, 2 >(2, 0);  
   i = 0;  
   for each ( MyClass2 ^ c in MyArray3 ) {  
      Console::Write("{0} = ", i++);  
      c -> Test();  
   }  
}  
```  
  
  **0 \= 在 MyClass**  
**1 \= 在 MyClass**  
**0 \= 在 MyClass2**  
**1 \= 在 MyClass2**  
**2 \= 在 MyClass2**  
**3 \= 在 MyClass2**   
## 範例  
 這個範例會逐一查看 <xref:System.Collections.ArrayList>中的每個顯示，實作 <xref:System.Collections.IEnumerable>。  
  
```  
// for_each_arrays_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Collections;  
  
int main() {  
   int retval = 0;  
  
   ArrayList ^ arr = gcnew ArrayList();  
   arr->Add(10);  
   arr->Add(20);  
   arr->Add(30);  
  
   for each ( int c in arr )  
      retval += c;  
   Console::WriteLine(retval);  
}  
```  
  
  **60**   
## 範例  
 這個範例顯示如何逐一查看陣列。  
  
```  
// for_each_arrays_3.cpp  
// compile with: /clr  
using namespace System;  
  
#define ARRAY_SIZE 2  
  
int main() {  
   int i, j;  
  
   // Declares an array of managed arrays of Int32.  
   array< array< Int32 > ^ > ^ IntArray = gcnew array<array< Int32 > ^>(ARRAY_SIZE);  
  
   for (i = 0 ; i < ARRAY_SIZE ; i++) {  
      IntArray[i] = gcnew array< Int32 >(ARRAY_SIZE);  
         for ( int j = 0 ; j < ARRAY_SIZE ; j++ )   
            IntArray[i][j] = i + 10;  
   }  
  
   for (i = 0 ; i < ARRAY_SIZE ; i++)  
      for (int j = 0 ; j < ARRAY_SIZE ; j++)  
         Console::WriteLine("IntArray[{0}] = {1}", i, IntArray[i][j]);  
   Console::WriteLine();  
  
   for each (array<Int32> ^ xyz in IntArray)  
      for each ( int c in xyz )  
         Console::WriteLine(c);  
}  
```  
  
  **IntArray \[0、\= 10**  
**IntArray \[0、\= 10**  
**IntArray \[1、\= 11**  
**IntArray \[1、\= 11**  
**10**  
**10**  
**11**  
**11**   
## 請參閱  
 [for each、in](../dotnet/for-each-in.md)