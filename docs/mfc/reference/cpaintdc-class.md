---
title: CPaintDC Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
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
ms.openlocfilehash: e70bf7a55f9a54ca3c2398a00c993a0aeec0f594
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cpaintdc-class"></a>CPaintDC Class
A device-context class derived from [CDC](../../mfc/reference/cdc-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPaintDC : public CDC  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CPaintDC::CPaintDC](#cpaintdc)|Constructs a `CPaintDC` connected to the specified [CWnd](../../mfc/reference/cwnd-class.md).|  
  
### <a name="public-data-members"></a>Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CPaintDC::m_ps](#m_ps)|Contains the [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) used to paint the client area.|  
  
### <a name="protected-data-members"></a>Protected Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CPaintDC::m_hWnd](#m_hwnd)|The `HWND` to which this `CPaintDC` object is attached.|  
  
## <a name="remarks"></a>Remarks  
 It performs a [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) at construction time and [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) at destruction time.  
  
 A `CPaintDC` object can only be used when responding to a [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message, usually in your `OnPaint` message-handler member function.  
  
 For more information on using `CPaintDC`, see [Device Contexts](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxwin.h  
  
##  <a name="cpaintdc"></a>  CPaintDC::CPaintDC  
 Constructs a `CPaintDC` object, prepares the application window for painting, and stores the [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) structure in the [m_ps](#m_ps) member variable.  
  
```  
explicit CPaintDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameters  
 `pWnd`  
 Points to the `CWnd` object to which the `CPaintDC` object belongs.  
  
### <a name="remarks"></a>Remarks  
 An exception (of type `CResourceException`) is thrown if the Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) call fails. A device context may not be available if Windows has already allocated all of its available device contexts. Your application competes for the five common display contexts available at any given time under Windows.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CPaintDC::m_hWnd  
 The `HWND` to which this `CPaintDC` object is attached.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Remarks  
 `m_hWnd` is a protected variable of type `HWND`.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]  
  
##  <a name="m_ps"></a>  CPaintDC::m_ps  
 `m_ps` is a public member variable of type [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md).  
  
```  
PAINTSTRUCT m_ps;  
```  
  
### <a name="remarks"></a>Remarks  
 It is the `PAINTSTRUCT` that is passed to and filled out by [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint).  
  
 The `PAINTSTRUCT` contains information that the application uses to paint the client area of the window associated with a `CPaintDC` object.  
  
 Note that you can access the device-context handle through the `PAINTSTRUCT`. However, you can access the handle more directly through the `m_hDC` member variable that `CPaintDC` inherits from `CDC`.  
  
### <a name="example"></a>Example  
  See the example for [CPaintDC::m_hWnd](#m_hwnd).  
  
## <a name="see-also"></a>See Also  
 [MFC Sample MDI](../../visual-cpp-samples.md)   
 [CDC Class](../../mfc/reference/cdc-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)




