---
title: 編譯器錯誤 C2013 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2013
dev_langs:
- C++
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53265c27bbac02ddbccb3b2a89b77a515e752f73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2013"></a>編譯器錯誤 C2013
遺漏 '>'  
  
 `#include` 指示詞缺少右角括弧。 加入右角括弧，以解決錯誤。  
  
 下列範例會產生 C2013：  
  
```  
// C2013.cpp  
#include <stdio.h    // C2013  
```  
  
 可能的解決方式：  
  
```  
// C2013b.cpp  
// compile with: /c  
#include <stdio.h>  
```