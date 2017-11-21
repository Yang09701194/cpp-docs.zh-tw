---
title: "編譯器錯誤 C2581 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2581
dev_langs: C++
helpviewer_keywords: C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 205d972237a71a05839dbc4236d248a11e6ee53d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2581"></a>編譯器錯誤 C2581
'type': 靜態 ' 運算子 =' 函式不合法  
  
 指派 (`=`) 運算子的宣告不正確地為`static`。 指派運算子不能`static`。 如需詳細資訊，請參閱[使用者定義的運算子 (C + + /CLI)](../../dotnet/user-defined-operators-cpp-cli.md)。  
  
## <a name="example"></a>範例  
 下列範例會產生 C2581。  
  
```  
// C2581.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y ^ operator = (Y^ me, int i);   // C2581  
   Y^ operator =(int i);   // OK  
};  
```