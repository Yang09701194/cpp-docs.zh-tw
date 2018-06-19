---
title: 'Cdynamicparameteraccessor:: Setparamlength |Microsoft 文件'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDynamicParameterAccessor::SetParamLength
- CDynamicParameterAccessor.SetParamLength
- ATL.CDynamicParameterAccessor.SetParamLength
- CDynamicParameterAccessor::SetParamLength
- SetParamLength
dev_langs:
- C++
helpviewer_keywords:
- SetParamLength method
ms.assetid: d8e0bbfe-e1ae-4a8f-9567-584fbb0c8385
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 01388944bc61912b5e31e95216259d76dc636284
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090610"
---
# <a name="cdynamicparameteraccessorsetparamlength"></a>CDynamicParameterAccessor::SetParamLength
設定儲存在緩衝區中的指定參數的長度。  
  
## <a name="syntax"></a>語法  
  
```
bool SetParamLength(DBORDINAL nParam,  
   DBLENGTH length);  ```  
  
#### Parameters  
 `nParam`  
 [in] The parameter number (offset from 1). Parameter 0 is reserved for return values. The parameter number is the index of the parameter based on its order in the SQL or stored procedure call. See [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) for an example.  
  
 *length*  
 [in] The length in bytes of the specified parameter.  
  
## Remarks  
 Returns **true** on success or **false** on failure.  
  
## Requirements  
 **Header:** atldbcli.h  
  
## See Also  
 [CDynamicParameterAccessor Class](../../data/oledb/cdynamicparameteraccessor-class.md)