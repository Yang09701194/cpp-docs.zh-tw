---
title: "編譯器錯誤 C3139 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3139
dev_langs: C++
helpviewer_keywords: C3139
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f47b4f642410b6e19db9f956260256c78410f86a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3139"></a>編譯器錯誤 C3139
'struct': 無法匯出 UDT 沒有成員  
  
 您嘗試將套用[匯出](../../windows/export.md)屬性設定為空的 UDT （使用者定義型別）。 例如:   
  
```  
// C3139.cpp  
#include "unknwn.h"  
[emitidl];  
[module(name=xx)];  
  
[export] struct MyStruct {   // C3139 empty type  
};  
int main(){}  
```