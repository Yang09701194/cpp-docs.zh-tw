---
title: CMFCFontComboBox Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
caps.latest.revision: 29
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
ms.openlocfilehash: dd8301564b5e28a4473184eb257879bc6ae7dd3b
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox Class
The `CMFCFontComboBox` class creates a combo box control that contains a list of fonts.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|Constructs a `CMFCFontComboBox` object.|  
|`CMFCFontComboBox::~CMFCFontComboBox`|Destructor.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCFontComboBox::CompareItem`|Called by the framework to determine the relative position of a new item in the sorted list box of the current font combo box control. (Overrides [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|  
|`CMFCFontComboBox::DrawItem`|Called by the framework to draw a specified item in the current font combo box control. (Overrides [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|  
|[CMFCFontComboBox::GetSelFont](#getselfont)|Retrieves information about the currently selected font.|  
|`CMFCFontComboBox::MeasureItem`|Called by the framework to inform Windows of the dimensions of the list box in the current font combo box control. (Overrides [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|  
|`CMFCFontComboBox::PreTranslateMessage`|Translates window messages before they are dispatched to the [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) and [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows functions. (Overrides [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCFontComboBox::SelectFont](#selectfont)|Selects the font that matches the specified criteria from the font combo box.|  
|[CMFCFontComboBox::Setup](#setup)|Initializes the list of items in the font combo box.|  
  
### <a name="data-members"></a>Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Indicates to the framework which font to use to draw the item labels in the current font combo box.|  
  
## <a name="remarks"></a>Remarks  
 To use a `CMFCFontComboBox` object in a dialog box, add a `CMFCFontComboBox` variable to the dialog box class. Then in the `OnInitDialog` method of the dialog box class, call the [CMFCFontComboBox::Setup](#setup) method to initialize the list of items in the combo box control.  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxfontcombobox.h  
  
##  <a name="cmfcfontcombobox"></a>  CMFCFontComboBox::CMFCFontComboBox  
 Constructs a `CMFCFontComboBox` object.  
  
```  
CMFCFontComboBox();
```  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getselfont"></a>  CMFCFontComboBox::GetSelFont  
 Retrieves information about the currently selected font.  
  
```  
CMFCFontInfo* GetSelFont() const;  
```  
  
### <a name="return-value"></a>Return Value  
 A pointer to [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md) object that describes a font. It can be `NULL` if no font is selected in the combo box.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_bdrawusingfont"></a>  CMFCFontComboBox::m_bDrawUsingFont  
 Indicates to the framework which font to use to draw the item labels in the current font combo box.  
  
```  
static BOOL m_bDrawUsingFont;  
```  
  
### <a name="remarks"></a>Remarks  
 Set this member to `TRUE` to direct the framework to use the same font to draw each item label. Set this member to `FALSE` to direct the framework to draw each item label with the font whose name is the same as the label. The default value of this member is `FALSE`.  
  
##  <a name="selectfont"></a>  CMFCFontComboBox::SelectFont  
 Selects the font that matches the specified criteria from the font combo box.  
  
```  
BOOL SelectFont(CMFCFontInfo* pDesc);

 
BOOL SelectFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDesc`  
 Points to a font description object.  
  
 [in] `lpszName`  
 Specifies a font name.  
  
 [in] `nCharSet`  
 Specifies a character set. The default value is DEFAULT_CHARSET. For more information, see the `lfCharSet` member of the [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) structure.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if an item in the font combo box matches the specified font description object or font name and charset; otherwise, `FALSE`.  
  
### <a name="remarks"></a>Remarks  
 Use this method to select and scroll to the item in the font combo box that corresponds to the specified font.  
  
### <a name="example"></a>Example  
 The following example demonstrates how to use the `SelectFont` method in the `CMFCFontComboBox` class. This example is part of the [New Controls sample](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]  
  
##  <a name="setup"></a>  CMFCFontComboBox::Setup  
 Initializes the list of items in the font combo box.  
  
```  
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `nFontType`  
 Specifies the font type. The default value is the bitwise combination (OR) of DEVICE_FONTTYPE, RASTER_FONTTYPE, and TRUETYPE_FONTTYPE.  
  
 [in] `nCharSet`  
 Specifies the font character set. The default value is DEFAULT_CHARSET.  
  
 [in] `nPitchAndFamily`  
 Specifies the font pitch and family. The default value is DEFAULT_PITCH.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the font combo box was initialized successfully; otherwise, `FALSE`.  
  
### <a name="remarks"></a>Remarks  
 This method initializes the font combo box by enumerating the currently installed fonts that match the specified parameters and inserting those font names in the font combo box.  
  
### <a name="example"></a>Example  
 The following example demonstrates how to use the `Setup` method in the `CMFCFontComboBox` class. This example is part of the [New Controls sample](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md)

