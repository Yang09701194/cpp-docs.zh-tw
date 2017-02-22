---
title: "CDynamicAccessor::Close | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicAccessor::Close"
  - "ATL.CDynamicAccessor.Close"
  - "CDynamicAccessor.Close"
  - "CDynamicAccessor::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close 方法"
ms.assetid: 2a28ded2-d7ed-4e80-90bf-143133c93feb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::Close
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

解除所有資料行的繫結，釋放配置的記憶體，並釋放類別中的 [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) 介面指標。  
  
## 語法  
  
```  
  
void Close( ) throw( );  
  
```  
  
## 需求  
 **標題:** atldbcli.h  
  
## 請參閱  
 [CDynamicAccessor 類別](../../data/oledb/cdynamicaccessor-class.md)