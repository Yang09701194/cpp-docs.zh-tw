---
title: "編譯器錯誤 C2766 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2766
dev_langs: C++
helpviewer_keywords: C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 795e2fe63a9252a5d6ab4b05f3666e975c997ebc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2766"></a>編譯器錯誤 C2766
明確特製化;'specialization' 已經定義  
  
 不允許重複的明確特製化。 如需詳細資訊，請參閱[明確特製化函式樣板的](../../cpp/explicit-specialization-of-function-templates.md)。  
  
 下列範例會產生 C2766:  
  
```  
// C2766.cpp  
// compile with: /c  
template<class T>   
struct A {};  
  
template<>   
struct A<int> {};  
  
template<>   
struct A<int> {};   // C2766  
// try the following line instead  
// struct A<char> {};  
```