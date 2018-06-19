---
title: 編譯器錯誤 C2793 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2793
dev_langs:
- C++
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea378b2a875542eab431cf9cc30217f50c971af6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236288"
---
# <a name="compiler-error-c2793"></a>編譯器錯誤 C2793
'token': 非預期的語彙基元下列 ':: '、 識別碼或關鍵字 'operator' 必須是  
  
 唯一的語彙基元時可遵循`__super::`是識別項或關鍵字`operator`。  
  
 下列範例會產生 C2793  
  
```  
// C2793.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::(); // C2793  
   }  
};  
```