---
title: "編譯器錯誤 C3365 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3365
dev_langs:
- C++
helpviewer_keywords:
- C3365
ms.assetid: 875ec3a4-522c-4e3d-9b67-48808b857f6d
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 2ad4d2d5b926001fad668b62b6cbf0abe21542c0
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3365"></a>編譯器錯誤 C3365
運算子 'operator' : 類型 'type1' 和 'type2' 的不同運算元  
  
已嘗試撰寫不同類型的委派。  請參閱[How to︰ 定義和使用委派 (C + + /cli CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)如需委派的詳細資訊。  
  
## <a name="example"></a>範例  
下列範例會產生 C3365：  
  
```cpp  
// C3365.cpp  
// compile with: /clr  
delegate void D1();  
delegate void D2(int);  
  
ref class R {  
public:  
   void f(){}  
   void g(int){}  
};  
  
int main() {  
   D1^ d1 = gcnew D1(gcnew R, &R::f);  
   D2^ d2 = gcnew D2(gcnew R, &R::g);  
   D1^ d3 = gcnew D1(gcnew R, &R::f);  
  
   d1 += d2;   // C3365  
   d1 += d3;   // OK  
   d1();  
}  
```
