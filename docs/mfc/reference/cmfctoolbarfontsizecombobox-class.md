---
title: CMFCToolBarFontSizeComboBox Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
caps.latest.revision: 26
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
ms.openlocfilehash: aa53b70eb9f152e8a4319613fa804c3296bfc0e2
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox Class
A toolbar button that contains a combo box control that enables the user to select a font size.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>Members  
  
### <a name="protected-constructors"></a>Protected Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Constructs a `CMFCToolBarFontSizeComboBox` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Returns the selected font size in twips.|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Fills the combo box list with all supported font sizes for a specified font.|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Sets the font size in twips.|  
  
## <a name="remarks"></a>Remarks  
 You can use a `CMFCToolBarFontSizeComboBox` object together with a [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md) object to enable a user to select a font and font size.  
  
 You can add a font size combo box button to a toolbar just as you add a font combo box button. For more information, see [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
 When the user selects a new font in a `CMFCToolBarFontComboBox` object, you can fill the font size combo box with the supported sizes for that font by using the [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) method.  
  
## <a name="example"></a>Example  
 The following example demonstrates how to use various methods in the `CMFCToolBarFontSizeComboBox` class to configure a `CMFCToolBarFontSizeComboBox` object. The example illustrates how to retrieve the font size, in twips, from the text box, fill the font size combo box with all valid sizes of the given font, and specify the font size in twips. This code snippet is part of the [Word Pad sample](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontsizecombobox"></a>  CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox  
 Constructs a `CMFCToolBarFontSizeComboBox` object.  
  
```  
CMFCToolBarFontSizeComboBox();
```  
  
##  <a name="gettwipsize"></a>  CMFCToolBarFontSizeComboBox::GetTwipSize  
 Retrieves the font size, in twips, from the text box of a font size combo box.  
  
```  
int GetTwipSize() const;  
```  
  
### <a name="return-value"></a>Return Value  
 If the return value is positive, it is the font size in twips. It is -1 if the text box of the combo box is empty. It is -2 if an error occurs.  
  
##  <a name="rebuildfontsizes"></a>  CMFCToolBarFontSizeComboBox::RebuildFontSizes  
 Fills a font size combo box with all valid sizes of the given font.  
  
```  
void RebuildFontSizes(const CString& strFontName);
```  
  
### <a name="parameters"></a>Parameters  
 `[in] strFontName`  
 Specifies a font name.  
  
### <a name="remarks"></a>Remarks  
 Call this function when you want to synchronize between selection in a font combo box and a font size combo box, such as a [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
##  <a name="settwipsize"></a>  CMFCToolBarFontSizeComboBox::SetTwipSize  
 Rounds the specified size (in twips) to the nearest size in points, and then sets the selected size in the combo box to that value.  
  
```  
void SetTwipSize(int nSize);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `nSize`  
 Specifies the font size (in twips) to set.  
  
### <a name="remarks"></a>Remarks  
 You can retrieve the previous valid font size later by calling the [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) method.  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Walkthrough: Putting Controls On Toolbars](../../mfc/walkthrough-putting-controls-on-toolbars.md)




