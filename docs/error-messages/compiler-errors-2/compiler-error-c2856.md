---
title: "編譯器錯誤 C2856 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2856
dev_langs:
- C++
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab5fdd09fbbd7c6b1f213404dfbf6d9d9e5612ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2856"></a>編譯器錯誤 C2856
\#pragma hdrstop 不可以是 #if 區塊內  
  
 `hdrstop` Pragma 不能放在條件式編譯區塊的主體內。  
  
 移動`#pragma hdrstop`陳述式，並未包含在區域`#if/#endif`區塊。