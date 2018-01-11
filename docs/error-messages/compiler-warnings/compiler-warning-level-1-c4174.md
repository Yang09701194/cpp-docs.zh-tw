---
title: "編譯器警告 （層級 1） C4174 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4174
dev_langs: C++
helpviewer_keywords: C4174
ms.assetid: 63301e51-24bc-43c4-bb11-252f7d513e9e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b270de3f0dd45486a46f67ce5582f603dfec32a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4174"></a>編譯器警告 (層級 1) C4174
'name': 無法當做 #pragma 元件使用  
  
## <a name="example"></a>範例  
  
```  
// C4174.cpp  
// compile with: /W1  
#pragma component(info)  // C4174; unknown  
#pragma component(browser, off)  // turn off browse info  
int main()  
{  
}  
```