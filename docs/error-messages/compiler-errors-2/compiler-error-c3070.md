---
title: 編譯器錯誤 C3070 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3070
dev_langs:
- C++
helpviewer_keywords:
- C3070
ms.assetid: ac88584d-40a6-4176-90f3-2371c3c935f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bacae42b6136364ed69d9ecad54a98e492f30bd8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248592"
---
# <a name="compiler-error-c3070"></a>編譯器錯誤 C3070
'property': 屬性沒有 'set' 方法  
  
 未定義屬性的 set 存取子方法。 如需詳細資訊，請參閱 [property](../../windows/property-cpp-component-extensions.md)。  
  
 下列範例會產生 C3070：  
  
```  
// C3070.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int size) {  
      m_data = gcnew array<int>(size);  
   }  
  
   property int % MyProp[int] {  
      int% get(int index) {   
         return m_data[index];   
      }  
   }  
  
   property int % MyProp2[int] {  
      int% get(int index) {   
         return m_data[index];  
      }  
      void set(int index, int % value) {}  
   }  
  
   property const int % MyProp3[int] {  
      const int% get(int index) {   
         return m_data[index];  
      }  
      void set(int index, const int % value) {}  
   }  
  
private:  
   array<int>^ m_data;  
};  
  
int main() {  
   R^ r = gcnew R(10);  
   r->MyProp[4] = 4;   // C3070  
  
   int value = 4;  
   r->MyProp2[4] = value;   // OK  
   r->MyProp3[4] = 4;   // OK  
}  
```