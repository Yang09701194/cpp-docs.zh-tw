---
title: CSimpleException Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
caps.latest.revision: 19
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
ms.openlocfilehash: 3ab6a2347567dfe404d3dc5c154e24c789dff45c
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="csimpleexception-class"></a>CSimpleException Class
This class is a base class for resource-critical MFC exceptions.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CSimpleException : public CException  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](#csimpleexception)|The constructor.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](#geterrormessage)|Provides text about an error that has occurred.|  
  
## <a name="remarks"></a>Remarks  
 `CSimpleException` is the base class for resource-critical MFC exceptions and handles the ownership and initialization of an error message. The following classes use `CSimpleException` as their base class:  
  
|||  
|-|-|  
|[CMemoryException Class](../../mfc/reference/cmemoryexception-class.md)|Out-of-memory exception|  
|[CNotSupportedException Class](../../mfc/reference/cnotsupportedexception-class.md)|Requests for an unsupported operation|  
|[CResourceException Class](../../mfc/reference/cresourceexception-class.md)|Windows resource not found or not creatable|  
|[CUserException Class](../../mfc/reference/cuserexception-class.md)|Exception that indicates a resource could not be found|  
|[CInvalidArgException Class](../../mfc/reference/cinvalidargexception-class.md)|Exception that indicates an invalid argument|  
  
 Because `CSimpleException` is an abstract base class, you cannot declare a `CSimpleException` object directly. Instead, you must declare derived objects such as those in the previous table. If you are declaring your own derived class, use the previous classes as a model.  
  
 For more information, see the [CException Class](../../mfc/reference/cexception-class.md) topic and [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afx.h  
  
##  <a name="csimpleexception"></a>  CSimpleException::CSimpleException  
 The constructor.  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Parameters  
 `bAutoDelete`  
 Specify **TRUE** if the memory for the `CSimpleException` object has been allocated on the heap. This will cause the `CSimpleException` object to be deleted when the **Delete** member function is called to delete the exception. Specify **FALSE** if the `CSimpleException` object is on the stack or is a global object. In this case, the `CSimpleException` object will not be deleted when the **Delete** member function is called.  
  
### <a name="remarks"></a>Remarks  
 You would normally never need to call this constructor directly. A function that throws an exception should create an instance of a `CException`-derived class and call its constructor, or it should use one of the MFC throw functions, such as [AfxThrowFileException](exception-processing.md#afxthrowfileexception), to throw a predefined type.  
  
##  <a name="geterrormessage"></a>  CSimpleException::GetErrorMessage  
 Call this member function to provide text about an error that has occurred.  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `lpszError`  
 A pointer to a buffer that will receive an error message.  
  
 `nMaxError`  
 The maximum number of characters the buffer can hold, including the **NULL** terminator.  
  
 `pnHelpContext`  
 The address of a **UINT** that will receive the help context ID. If **NULL**, no ID will be returned.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the function is successful; otherwise 0 if no error message text is available.  
  
### <a name="remarks"></a>Remarks  
 For more information, see [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Exception Handling](../../mfc/exception-handling-in-mfc.md)




