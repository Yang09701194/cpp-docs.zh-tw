---
title: "_pAtlModule | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATLBASE/_pAtlModule"
  - "_pAtlModule"
  - "ATL::_pAtlModule"
  - "ATL._pAtlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pAtlModule variable"
  - "pAtlModule variable"
ms.assetid: 0ecde3a9-3f4d-4c7b-bb54-713ce05c4777
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _pAtlModule
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

儲存指標的全域變數為目前的模組。  
  
## 語法  
  
```  
__declspec(selectany) CAtlModule * _pAtlModule  
```  
  
## 備註  
 在這個全域變數的方法可用來提供功能 \(現在已經過時\) 類別 [CComModule](../../atl/reference/ccommodule-class.md) Visual C\+\+ 6.0 提供了。  
  
## 範例  
 [!code-cpp[NVC_ATL_Windowing#97](../../atl/codesnippet/CPP/patlmodule_1.cpp)]  
  
## 需求  
 **Header:** atlbase.h  
  
## 請參閱  
 [Global Variables](../../atl/reference/atl-global-variables.md)