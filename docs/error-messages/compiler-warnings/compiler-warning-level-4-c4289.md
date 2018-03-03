---
title: "編譯器警告 （層級 4） C4289 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4289
dev_langs:
- C++
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 98acda62a984f2625ddc742e309aca7628d9c9f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4289"></a>編譯器警告 (層級 4) C4289
使用非標準的擴充：'var' : 在 for-loop 範圍外使用 for-loop 中所宣告的迴圈控制變數  
  
 編譯時[/Ze](../../build/reference/za-ze-disable-language-extensions.md)和**/zc: forscope-**，在宣告的變數[的](../../cpp/for-statement-cpp.md)之後已使用迴圈**的**-迴圈範圍。  
  
 請參閱[/zc: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)如需有關如何指定標準行為資訊**如**迴圈以**/Ze**。  
  
 此警告預設為關閉。 如需詳細資訊，請參閱 [預設為關閉的編譯器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 。  
  
 下列範例會產生 C4289:  
  
```  
// C4289.cpp  
// compile with: /W4 /Zc:forScope-  
#pragma warning(default:4289)  
int main() {  
   for (int i = 0 ; ; )   // C4289  
      break;  
   i++;  
}  
```