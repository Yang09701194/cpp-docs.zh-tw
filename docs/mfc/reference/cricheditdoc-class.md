---
title: CRichEditDoc Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
dev_langs:
- C++
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
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
ms.openlocfilehash: 1191752e58ac546cc98fae4f3f2b882d94c8e076
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cricheditdoc-class"></a>CRichEditDoc Class
With [CRichEditView](../../mfc/reference/cricheditview-class.md) and [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), provides the functionality of the rich edit control within the context of MFC's document view architecture.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRichEditDoc : public COleServerDoc  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](#createclientitem)|Called to perform cleanup of the document.|  
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Indicates whether stream input and output should include formatting information.|  
|[CRichEditDoc::GetView](#getview)|Retrieves the asssociated [CRichEditView](../../mfc/reference/cricheditview-class.md) object.|  
  
### <a name="public-data-members"></a>Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditDoc::m_bRTF](#m_brtf)|Indicates whether stream I/O should include formatting.|  
  
## <a name="remarks"></a>Remarks  
 A "rich edit control" is a window in which the user can enter and edit text. The text can be assigned character and paragraph formatting, and can include embedded OLE objects. Rich edit controls provide a programming interface for formatting text. However, an application must implement any user interface components necessary to make formatting operations available to the user.  
  
 `CRichEditView` maintains the text and formatting characteristic of text. `CRichEditDoc` maintains the list of client items which are in the view. `CRichEditCntrItem` provides container-side access to the OLE client items.  
  
 This Windows Common control (and therefore the [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) and related classes) is available only to programs running under Windows 95/98 and Windows NT versions 3.51 and later.  
  
 For an example of using a rich edit document in an MFC application, see the [WORDPAD](../../visual-cpp-samples.md) sample application.  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxrich.h  
  
##  <a name="createclientitem"></a>  CRichEditDoc::CreateClientItem  
 Call this function to create a `CRichEditCntrItem` object and add it to this document.  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>Parameters  
 *preo*  
 Pointer to an [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) structure which describes an OLE item. The new `CRichEditCntrItem` object is constructed around this OLE item. If *preo* is **NULL**, the new client item is empty.  
  
### <a name="return-value"></a>Return Value  
 Pointer to a new [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) object which has been added to this document.  
  
### <a name="remarks"></a>Remarks  
 This function does not perform any OLE initialization.  
  
 For more information, see the [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) structure in the Windows SDK.  
  
##  <a name="getstreamformat"></a>  CRichEditDoc::GetStreamFormat  
 Call this function to determine the text format for streaming the contents of the rich edit.  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>Return Value  
 One of the following flags:  
  
- `SF_TEXT` Indicates that the rich edit control does not maintain formatting information.  
  
- `SF_RTF` Indicates that the rich edit control does maintain formatting information.  
  
### <a name="remarks"></a>Remarks  
 The return value is based on the [m_bRTF](#m_brtf) data member. This function returns `SF_RTF` if `m_bRTF` is **TRUE**; otherwise, `SF_TEXT`.  
  
##  <a name="getview"></a>  CRichEditDoc::GetView  
 Call this function to access the [CRichEditView](../../mfc/reference/cricheditview-class.md) object associated with this `CRichEditDoc` object.  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Pointer to the `CRichEditView` object associated with the document.  
  
### <a name="remarks"></a>Remarks  
 The text and formatting information are contained within the `CRichEditView` object. The `CRichEditDoc` object maintains the OLE items for serialization. There should be only one `CRichEditView` for each `CRichEditDoc`.  
  
##  <a name="m_brtf"></a>  CRichEditDoc::m_bRTF  
 When **TRUE**, indicates that [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) and [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) should store paragraph and character-formatting characteristics.  
  
```  
BOOL m_bRTF;  
```  
  
## <a name="see-also"></a>See Also  
 [MFC Sample WORDPAD](../../visual-cpp-samples.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem Class](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl Class](../../mfc/reference/cricheditctrl-class.md)

