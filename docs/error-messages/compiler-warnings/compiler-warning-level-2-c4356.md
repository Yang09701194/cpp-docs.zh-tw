---
title: "編譯器警告 （層級 2） C4356 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4356
dev_langs: C++
helpviewer_keywords: C4356
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fa186aff5d2e54c3ac9444303067a223702fbb2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4356"></a>編譯器警告 (層級 2) C4356
'member': 無法透過衍生類別初始化靜態資料成員  
  
 初始化靜態資料成員的格式不正確。 編譯器會接受初始化。 若要避免這個警告，初始化透過基底類別成員。  
  
 使用[警告](../../preprocessor/warning.md)pragma 可隱藏這個警告。  
  
 下列範例會產生 C4356:  
  
```  
// C4356.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
  
template <class T>  
class C {  
   static int n;  
};  
  
class D : C<int> {};  
  
int D::n = 0; // C4356  
// try the following line instead  
// int C<int>::n = 0;  
  
class A {  
public:  
   static int n;  
};  
  
class B : public A {};  
  
int B::n = 10;   // C4356  
// try the following line instead  
// int A::n = 99;  
  
int main() {  
   using namespace std;  
   cout << B::n << endl;  
}  
```