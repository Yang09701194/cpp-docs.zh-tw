---
title: "編譯器錯誤 C3368 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3368
dev_langs: C++
helpviewer_keywords: C3368
ms.assetid: 5bfd5be4-dfa9-4b33-9612-010561b40955
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f3986520ecba799f77fe221d16c99d9d621bf67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3368"></a>編譯器錯誤 C3368
'function declaration' : IDL 的無效呼叫慣例  
  
 .idl 檔中只能使用 [__stdcall](../../cpp/stdcall.md) 或 [__cdecl](../../cpp/cdecl.md) 呼叫慣例。  
  
 下列範例會產生 C3368：  
  
```  
// C3368.cpp  
// processor: x86  
[idl_module(name="Name", dllname="Some.dll")];  
  
[idl_module(name="Name")]  
int __fastcall f1();   // C3368  
```