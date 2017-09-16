---
title: CMFCRibbonButtonsGroup Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
caps.latest.revision: 34
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: MT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 24349fa0775db80b5e0365525cee4954c9e0d7b8
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup Class
The `CMFCRibbonButtonsGroup` class allows you to organize a set of ribbon buttons into a group. All buttons in the group are directly adjacent to each other horizontally and enclosed in a border.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Constructs a `CMFCRibbonButtonsGroup` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|Adds a button to a group.|  
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|Adds a list of buttons to a group.|  
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|Returns a pointer to the button that is located at a specified index.|  
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Returns the number of buttons in the group.|  
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Returns the image size of the normal images in the ribbon group (overrides [CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Returns the regular size of the ribbon element (overrides [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Reports whether the `CMFCRibbonButtonsGroup` object contains toolbar images.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Draws the appropriate image for a specified button, depending on whether the button is normal, highlighted or disabled.|  
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Removes all buttons from the `CMFCRibbonButtonsGroup` object.|  
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Assigns images to the group.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Sets the parent `CMFCRibbonCategory` of the `CMFCRibbonButtonsGroup` object and all the buttons within it (overrides [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
  
## <a name="remarks"></a>Remarks  
 The group is derived from [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) and can be manipulated as a single entity. You can position the group on any panel or popup menu.  
  
## <a name="example"></a>Example  
 The following example demonstrates how to use various methods in the `CMFCRibbonButtonsGroup` class. The example shows how to construct a `CMFCRibbonButtonsGroup` object, assign images to the group of ribbon buttons, and add a button to the group of ribbon buttons. This code snippet is part of the [Draw Client sample](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxribbonbuttonsgroup.h  
  
##  <a name="addbutton"></a>  CMFCRibbonButtonsGroup::AddButton  
 Adds a button to a group.  
  
```  
void AddButton(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pButton`  
 A pointer to a button to add.  
  
##  <a name="addbuttons"></a>  CMFCRibbonButtonsGroup::AddButtons  
 Adds a list of buttons to a group.  
  
```  
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `lstButtons`  
 A list of pointers to the buttons that you want to add.  
  
##  <a name="cmfcribbonbuttonsgroup"></a>  CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup  
 Constructs a `CMFCRibbonButtonsGroup` object.  
  
```  
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pButton`  
 Specifies a button to add to the newly created `CMFCRibbonButtonsGroup` object.  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getbutton"></a>  CMFCRibbonButtonsGroup::GetButton  
 Returns a pointer to the button that is located at a specified index.  
  
```  
CMFCRibbonBaseElement* GetButton(int i) const;  
```  
  
### <a name="parameters"></a>Parameters  
 [in] `i`  
 A zero-based index of a button to return.  
  
### <a name="return-value"></a>Return Value  
 A pointer to the button that is located at the specified index. `NULL` if the specified index is out of range.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcount"></a>  CMFCRibbonButtonsGroup::GetCount  
 Returns the number of buttons in the group.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The number of buttons in the group.  
  
##  <a name="getimagesize"></a>  CMFCRibbonButtonsGroup::GetImageSize  
 Retrieves the source image size of the protected `CMFCToolBarImages` member `m_Images`.  
  
```  
const CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Returns the source image size of the toolbar images, if any are present, or a `CSize` of zero if not.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getregularsize"></a>  CMFCRibbonButtonsGroup::GetRegularSize  
 Retrieves the maximum possible size of the ribbon group element.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 Pointer to the device context of the ribbon group.  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="hasimages"></a>  CMFCRibbonButtonsGroup::HasImages  
 Reports whether the `CMFCRibbonButtonsGroup` object contains toolbar images.  
  
```  
BOOL HasImages() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Returns TRUE if the protected `CMFCToolBarImages` member `m_Images` contains any images, or FALSE if not.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ondrawimage"></a>  CMFCRibbonButtonsGroup::OnDrawImage  
 Draws the appropriate image for a specified button, depending on whether the button is normal, highlighted or disabled.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rectImage,  
    CMFCRibbonBaseElement* pButton,  
    int nImageIndex);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 Pointer to the device context of the `CMFCRibbonButtonsGroup` object.  
  
 [in] `rectImage`  
 The rectangle within which to draw the image.  
  
 [in] `pButton`  
 The button for which to draw the image.  
  
 [in] `nImageIndex`  
 The index of the image to draw on the button (in one of the three image arrays for normal, highlighted or disabled buttons).  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="removeall"></a>  CMFCRibbonButtonsGroup::RemoveAll  
 Removes all buttons from the `CMFCRibbonButtonsGroup` object.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setimages"></a>  CMFCRibbonButtonsGroup::SetImages  
 Assigns images to the group of ribbon buttons.  
  
```  
void SetImages(
    CMFCToolBarImages* pImages,  
    CMFCToolBarImages* pHotImages,  
    CMFCToolBarImages* pDisabledImages);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pImages`  
 Regular images.  
  
 [in] `pHotImages`  
 Hot images.  
  
 [in] `pDisabledImages`  
 Disabled images.  
  
### <a name="remarks"></a>Remarks  
 Call `SetImages` before you add buttons to a group. The number of images must be greater or equal to the number of buttons to be added to the group.  
  
> [!NOTE]
>  Hot images are images that are displayed when the user hovers over the button. Disabled images are images that are displayed when the button is disabled.  
  
##  <a name="setparentcategory"></a>  CMFCRibbonButtonsGroup::SetParentCategory  
 Sets the parent `CMFCRibbonCategory` of the `CMFCRibbonButtonsGroup` object and all the buttons within it.  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pCategory`  
 Pointer to the parent category to set (the tabbed groups in ribbon controls are called categories).  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

