---
title: "編譯器警告 （層級 4） C4343 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4343
dev_langs:
- C++
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: a67b44c766f51acb7a9d4cacc94448f1b4594c3e
ms.contentlocale: zh-tw
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4343"></a>編譯器警告 (層級 4) C4343
\#pragma optimize("g",off) 覆寫了 /Og 選項  
  
 這個警告，只在 Itanium 處理器系列 (IPF) 編譯器，有效報告 pragma[最佳化](../../preprocessor/optimize.md)已覆寫[/Og](../../build/reference/og-global-optimizations.md)編譯器選項。  
  
 下列範例會產生 C4343：  
  
```  
// C4343.cpp  
// compile with: /Og /W4 /LD  
// processor: IPF  
#pragma optimize ("g", off)   // C4343  
```
