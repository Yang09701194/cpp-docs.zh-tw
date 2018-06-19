---
title: 編譯器警告 （層級 1） C4659 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4659
dev_langs:
- C++
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 643b599cd11d0935f1769ad37dca4e764f0418e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285612"
---
# <a name="compiler-warning-level-1-c4659"></a>編譯器警告 (層級 1) C4659
\#pragma 'pragma': 使用保留的區段 'segment' 有未定義的行為，請使用 #pragma 註解 (linker，...)  
  
 將選項傳遞至連結器用以.drectve 選項。 改為使用 pragma[註解](../../preprocessor/comment-c-cpp.md)傳遞連結器選項。  
  
```  
// C4659.cpp  
// compile with: /W1 /LD  
#pragma code_seg(".drectve")   // C4659  
```