---
title: COleException Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
dev_langs:
- C++
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
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
ms.openlocfilehash: 2da980774095b3ee94284e4cfe72263e92db70df
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="coleexception-class"></a>COleException Class
Represents an exception condition related to an OLE operation.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleException : public CException  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[COleException::Process](#process)|Translates a caught exception into an OLE return code.|  
  
### <a name="public-data-members"></a>Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|Contains the status code that indicates the reason for the exception.|  
  
## <a name="remarks"></a>Remarks  
 The `COleException` class includes a public data member that holds the status code indicating the reason for the exception.  
  
 In general, you should not create a `COleException` object directly; instead, you should call [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 For more information on exceptions, see the articles [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md) and [Exceptions: OLE Exceptions](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxdisp.h  
  
##  <a name="m_sc"></a>  COleException::m_sc  
 This data member holds the OLE status code that indicates the reason for the exception.  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>Remarks  
 This variable's value is set by [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 For more information on `SCODE`, see [Structure of COM Error Codes](http://msdn.microsoft.com/library/windows/desktop/ms690088) in the Windows SDK.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="process"></a>  COleException::Process  
 Call the **Process** member function to translate a caught exception into an OLE status code.  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>Parameters  
 *pAnyException*  
 Pointer to a caught exception.  
  
### <a name="return-value"></a>Return Value  
 An OLE status code.  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  This function is **static**.  
  
 For more information on `SCODE`, see [Structure of COM Error Codes](http://msdn.microsoft.com/library/windows/desktop/ms690088) in the Windows SDK.  
  
### <a name="example"></a>Example  
  See the example for [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
## <a name="see-also"></a>See Also  
 [MFC Sample CALCDRIV](../../visual-cpp-samples.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)




