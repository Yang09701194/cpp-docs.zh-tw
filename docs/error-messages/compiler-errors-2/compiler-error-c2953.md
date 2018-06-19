---
title: 編譯器錯誤 C2953 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2953
dev_langs:
- C++
helpviewer_keywords:
- C2953
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 403ebce4fdb8b3ff8cf014c27cfc6ec988a1a897
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245106"
---
# <a name="compiler-error-c2953"></a>編譯器錯誤 C2953
'identifier': 類別樣板已經定義過了  
  
 請檢查原始程式碼檔並包含其他定義的檔案。  
  
 下列範例會產生 C2953：  
  
```  
// C2953.cpp  
// compile with: /c  
template <class T>  class A {};  
template <class T>  class A {};   // C2953  
template <class T>  class B {};   // OK  
```