---
title: 編譯器錯誤 C3638 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3638
dev_langs:
- C++
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3edb1a05323187b4a5dfcc2356da4a1ff8b874de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3638"></a>編譯器錯誤 C3638
'operator': 無法重新定義標準的 boxing 和 unboxing 轉換運算子  
  
 編譯器定義轉換運算子，針對每個 managed 類別來支援隱含 boxing。 這個運算子不能重新定義。  
  
 如需詳細資訊，請參閱[隱含 Boxing](../../windows/boxing-cpp-component-extensions.md)。  
  
 下列範例會產生 C3638:  
  
```  
// C3638.cpp  
// compile with: /clr  
value struct V {  
   V(){}  
   static operator V^(V);   // C3638  
};  
  
int main() {  
   V myV;  
   V ^ pmyV = myV;   // operator supports implicit boxing  
}  
```