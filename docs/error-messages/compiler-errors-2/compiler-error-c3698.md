---
title: 編譯器錯誤 C3698 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3698
dev_langs:
- C++
helpviewer_keywords:
- C3698
ms.assetid: 3c02fb08-7ba4-4637-a06f-19926cb2b5f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b41b0f7360d49891e330277114324aa099900682
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33263969"
---
# <a name="compiler-error-c3698"></a>編譯器錯誤 C3698
'type': 無法使用此類型為 'operator' 的引數  
  
 受管理的物件宣告不正確。  
  
 下列範例會產生 C3698:  
  
```  
// C3698.cpp  
// compile with: /clr  
  
int main() {  
   array<int>^a = new array<int>^(20);   // C3698  
   array<int>^a2 = gcnew array<int>(20);   // OK  
}  
```