---
title: CDBPropIDSet::SetGUID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- SetGUID method
ms.assetid: 8dd0f3bf-1490-4d53-9063-322b8d821bbe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 807b4cf13c01952ed811e6a7058eaf974e685154
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2018
---
# <a name="cdbpropidsetsetguid"></a>CDBPropIDSet::SetGUID
設定中的 GUID 欄位**DBPROPIDSET**結構。  
  
## <a name="syntax"></a>語法  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>參數  
 `guid`  
 [in]若要設定使用 GUID **guidPropertySet**欄位[DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx)結構。  
  
## <a name="remarks"></a>備註  
 這個欄位可以設定[建構函式](../../data/oledb/cdbpropidset-cdbpropidset.md)以及。 如果您為這個類別使用預設建構函式，則呼叫此函式。  
  
## <a name="requirements"></a>需求  
 **標題:** atldbcli.h  
  
## <a name="see-also"></a>請參閱  
 [CDBPropIDSet 類別](../../data/oledb/cdbpropidset-class.md)