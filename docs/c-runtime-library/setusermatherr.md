---
title: "__setusermatherr | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__setusermatherr"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__setusermatherr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__setusermatherr"
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __setusermatherr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定使用者提供的常式以處理算術錯誤，而不是使用 [\_matherr](../c-runtime-library/reference/matherr.md) 常式。  
  
## 語法  
  
```cpp  
void __setusermatherr(  
   _HANDLE_MATH_ERROR pf   
   )  
  
```  
  
#### 參數  
 `pf`  
 指向使用者提供 `_matherr` 實作的指標。  
  
 `pf` 參數的型別宣告為 `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)`。  
  
## 備註  
  
## 需求  
  
|常式|必要的標頭|  
|--------|-----------|  
|\_\_setusermatherr|matherr.c|