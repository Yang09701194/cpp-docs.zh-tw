---
title: CNotSupportedException Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs:
- C++
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: 20
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
ms.openlocfilehash: 83bc88d4618939650296e73a1c991b6e75883272
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cnotsupportedexception-class"></a>CNotSupportedException Class
Represents an exception that is the result of a request for an unsupported feature.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CNotSupportedException : public CSimpleException  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|Constructs a `CNotSupportedException` object.|  
  
## <a name="remarks"></a>Remarks  
 No further qualification is necessary or possible.  
  
 For more information on using `CNotSupportedException`, see the article [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afx.h  
  
##  <a name="cnotsupportedexception"></a>  CNotSupportedException::CNotSupportedException  
 Constructs a `CNotSupportedException` object.  
  
```  
CNotSupportedException();
```  
  
### <a name="remarks"></a>Remarks  
 Do not use this constructor directly, but rather call the global function [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception). for more information about exception processing, see the article [Exception Handling in MFC](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>See Also  
 [CException Class](cexception-class.md)   
 [Hierarchy Chart](../hierarchy-chart.md)



