---
title: "Irowsetimpl:: M_bcanscrollback |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl::m_bCanScrollBack
- ATL::IRowsetImpl::m_bCanScrollBack
- IRowsetImpl.m_bCanScrollBack
- ATL.IRowsetImpl.m_bCanScrollBack
- m_bCanScrollBack
dev_langs: C++
helpviewer_keywords: m_bCanScrollBack
ms.assetid: 69de3179-bf56-415e-935f-e98bcb34debe
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2f0fd3e481033947ddce11193872085b553d5ff7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplmbcanscrollback"></a>IRowsetImpl::m_bCanScrollBack
指出是否提供者都會有其資料指標捲動回溯。  
  
## <a name="syntax"></a>語法  
  
```  
  
unsigned  m_bCanScrollBack:1;  
  
```  
  
## <a name="remarks"></a>備註  
 連結至此網站**DBPROP_CANSCROLLBACKWARDS**屬性**DBPROPSET_ROWSET**群組。 提供者必須支援**DBPROP_CANSCROLLBACKWARDS**如**m_bCanFetchBackwards**即為 true。  
  
## <a name="requirements"></a>需求  
 **Header:** atldb.h  
  
## <a name="see-also"></a>請參閱  
 [IRowsetImpl 類別](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::m_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)