---
title: "編譯器錯誤 C3733 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3733
dev_langs: C++
helpviewer_keywords: C3733
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dedd36afd3b0211148c61ee3279d77eb25273c50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3733"></a>編譯器錯誤 C3733
'event': 不適當的語法指定 COM 事件。您是否忘記 '__interface'？  
  
 錯誤的語法用於 COM 事件。 若要修正這個錯誤，變更的事件類型，或更正語法，以遵守 COM 事件規則。  
  
 下列範例會產生 C3733:  
  
```  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[coclass, event_source(com), // change 'com' to 'native' to resolve  
uuid("00000000-0000-0000-0000-000000000001")]  
class A  
{  
   __event void func();   // C3733  
};  
  
int main()  
{  
}  
```