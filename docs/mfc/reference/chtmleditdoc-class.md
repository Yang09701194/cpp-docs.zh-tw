---
title: CHtmlEditDoc Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
caps.latest.revision: 24
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
ms.openlocfilehash: 82ed2f0bf3c702919a50a2240706496ea2885740
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc Class
With [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), provides the functionality of the WebBrowser editing platform within the context of the MFC document-view architecture.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|Constructs a `CHtmlEditDoc` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CHtmlEditDoc::GetView](#getview)|Retrieves the `CHtmlEditView` object attached to this document.|  
|[CHtmlEditDoc::IsModified](#ismodified)|Returns whether the associated view's WebBrowser control contains a document that has been modified by the user.|  
|[CHtmlEditDoc::OpenURL](#openurl)|Opens a URL.|  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `CHtmlEditDoc`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxhtml.h  
  
##  <a name="chtmleditdoc"></a>  CHtmlEditDoc::CHtmlEditDoc  
 Constructs a **CHtmlEditDoc** object.  
  
```  
CHtmlEditDoc();
```  
  
##  <a name="getview"></a>  CHtmlEditDoc::GetView  
 Retrieves the [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) object attached to this document.  
  
```  
virtual CHtmlEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Returns a pointer to the document's **CHtmlEditView** object.  
  
##  <a name="ismodified"></a>  CHtmlEditDoc::IsModified  
 Returns whether the associated view's WebBrowser control contains a document that has been modified by the user.  
  
```  
virtual BOOL IsModified();
```  
  
##  <a name="openurl"></a>  CHtmlEditDoc::OpenURL  
 Opens a URL.  
  
```  
virtual BOOL OpenURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Parameters  
 `lpszURL`  
 The URL to open.  
  
### <a name="return-value"></a>Return Value  
 Returns **TRUE** on success, **FALSE** on failure.  
  
## <a name="see-also"></a>See Also  
 [HTMLEdit Sample](../../visual-cpp-samples.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)


