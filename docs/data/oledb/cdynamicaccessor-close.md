---
title: CDynamicAccessor::Close | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDynamicAccessor::Close
- ATL.CDynamicAccessor.Close
- CDynamicAccessor.Close
- CDynamicAccessor::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 2a28ded2-d7ed-4e80-90bf-143133c93feb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7fb83230b3dda03ee179872d34cf2515ac5d1f2a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicaccessorclose"></a>CDynamicAccessor::Close
所有資料行解除繫結，釋放配置的記憶體，並釋放[IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx)類別中的介面指標。  
  
## <a name="syntax"></a>語法  
  
```cpp
void Close() throw();  
  
```  
  
## <a name="requirements"></a>需求  
 **標題:** atldbcli.h  
  
## <a name="see-also"></a>請參閱  
 [CDynamicAccessor 類別](../../data/oledb/cdynamicaccessor-class.md)