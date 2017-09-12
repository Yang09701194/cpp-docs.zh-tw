---
title: CResourceException Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
dev_langs:
- C++
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: e177da6dbaabd6cd96f0a5e61303a6194bf7ba6d
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cresourceexception-class"></a>CResourceException Class
Generated when Windows cannot find or allocate a requested resource.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CResourceException : public CSimpleException  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CResourceException::CResourceException](#cresourceexception)|Constructs a `CResourceException` object.|  
  
## <a name="remarks"></a>Remarks  
 No further qualification is necessary or possible.  
  
 For more information on using `CResourceException`, see the article [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxwin.h  
  
##  <a name="cresourceexception"></a>  CResourceException::CResourceException  
 Constructs a `CResourceException` object.  
  
```  
CResourceException();
```  
  
### <a name="remarks"></a>Remarks  
 Do not use this constructor directly, but rather call the global function [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception). for more information about exceptions, see the article [Exception Handling in MFC](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>See Also  
 [CException Class](cexception-class.md)   
 [Hierarchy Chart](../hierarchy-chart.md)



