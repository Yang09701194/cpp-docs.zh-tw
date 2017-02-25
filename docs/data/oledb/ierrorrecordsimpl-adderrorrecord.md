---
title: "IErrorRecordsImpl::AddErrorRecord | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorRecordsImpl.AddErrorRecord"
  - "AddErrorRecord"
  - "IErrorRecordsImpl::AddErrorRecord"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddErrorRecord 方法"
ms.assetid: b5f8e9ae-509d-454f-b511-4bda7e972607
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IErrorRecordsImpl::AddErrorRecord
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

將資料錄加入至 OLE DB 錯誤物件。  
  
## 語法  
  
```  
  
      STDMETHOD( AddErrorRecord )(  
   ERRORINFO *pErrorInfo,  
   DWORD dwLookupID,  
   DISPPARAMS *pdispparams,  
   IUnknown *punkCustomError,  
   DWORD dwDynamicErrorID   
);  
```  
  
#### 參數  
 請參閱《 *OLE DB 程式設計人員參考》的*[IErrorRecords::AddErrorRecord](https://msdn.microsoft.com/en-us/library/ms725362.aspx) 。  
  
## 需求  
 **Header:** atldb.h  
  
## 請參閱  
 [IErrorRecordsImpl 類別](../../data/oledb/ierrorrecordsimpl-class.md)