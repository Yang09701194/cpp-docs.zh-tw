---
title: CMFCRibbonColorButton Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
caps.latest.revision: 36
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
ms.openlocfilehash: 5b5a35d73ae0680dbbd5ada9006c9c50202aff06
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton Class
The `CMFCRibbonColorButton` class implements a color button that you can add to a ribbon bar. The ribbon color button displays a drop-down menu that contains one or more color palettes.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|Adds a group of colors to the regular color area.|  
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|Specifies whether the **Automatic** button is enabled.|  
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|Enables the **Other** button.|  
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||  
|[CMFCRibbonColorButton::GetColor](#getcolor)|Returns the currently selected color.|  
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|Returns the size of the color elements that appear on the color bar.|  
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||  
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|Returns the color of the currently selected element on the popup color palette.|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|Removes all color groups from the regular color area.|  
|[CMFCRibbonColorButton::SetColor](#setcolor)|Selects a color from the regular color area.|  
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|Sets the size of all the color elements that appear on the color bar.|  
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||  
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||  
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|Specifies a list of RGB values to display in the document color area.|  
|[CMFCRibbonColorButton::SetPalette](#setpalette)||  
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||  
  
## <a name="remarks"></a>Remarks  
 The ribbon color button displays a color bar when a user presses it. By default, this color bar contains a color selection palette called the regular color area. Optionally, the color bar can display an **Automatic** button, which allows the user to select a default color, and an **Other** button, which displays a popup color palette that contains additional colors.  
  
## <a name="example"></a>Example  
 The following example demonstrates how to use various methods in the `CMFCRibbonColorButton` class. The example shows how to construct a `CMFCRibbonColorButton` object, set the large image, enable the **Automatic** button, enable the **Other** button, set the number of columns, set the size of all the color elements that appear on the color bar, add a group of colors to the regular color area, and specify a list of RGB values to display in the document color area. This code snippet is part of the [Draw Client sample](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxribboncolorbutton.h  
  
##  <a name="addcolorsgroup"></a>  CMFCRibbonColorButton::AddColorsGroup  
 Adds a group of colors to the regular color area.  
  
```  
void AddColorsGroup(
    LPCTSTR lpszName,  
    const CList<COLORREF,COLORREF>& lstColors,  
    BOOL bContiguousColumns=FALSE);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `lpszName`  
 The group name.  
  
 [in] `lstColors`  
 The list of colors.  
  
 [in] `bContiguousColumns`  
 Controls how the color items are displayed in the group. If `TRUE`, the color items are drawn without a vertical spacing. If `FALSE`, the color items are drawn with a vertical spacing.  
  
### <a name="remarks"></a>Remarks  
 Use this function to make the color pop-up display several groups of colors. You can control how the colors are displayed in group.  
  
##  <a name="cmfcribboncolorbutton"></a>  CMFCRibbonColorButton::CMFCRibbonColorButton  
 Constructs a `CMFCRibbonColorButton` object.  
  
```  
CMFCRibbonColorButton();

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    COLORREF color = RGB(0, 0, 0));

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    BOOL bSimpleButtonLook,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    COLORREF color = RGB(0, 0, 0));
```  
  
### <a name="parameters"></a>Parameters  
 [in] `nID`  
 Specifies the command ID of the command to execute when a user clicks the button.  
  
 [in] `lpszText`  
 Specifies the text to appear on the button.  
  
 [in] `nSmallImageIndex`  
 The zero-based index of the small image to appear on the button.  
  
 [in] `color`  
 The color of the button (defaults to black).  
  
 [in] `bSimpleButtonLook`  
 If `TRUE`, the button is drawn as a simple rectangle.  
  
 [in] `nLargeImageIndex`  
 The zero-based index of the large image to appear on the button.  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="enableautomaticbutton"></a>  CMFCRibbonColorButton::EnableAutomaticButton  
 Specifies whether the **Automatic** button is enabled.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE,  
    LPCTSTR lpszToolTip=NULL,  
    BOOL bOnTop=TRUE,  
    BOOL bDrawBorder=FALSE);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `lpszLabel`  
 The label for the **Automatic** button.  
  
 [in] `colorAutomatic`  
 An RGB value that specifies the **Automatic** button's default color.  
  
 [in] `bEnable`  
 `TRUE` if the **Automatic** button is enabled; `FALSE` if it is disabled.  
  
 [in] `lpszToolTip`  
 The tooltip of the **Automatic** button.  
  
 [in] `bOnTop`  
 Specifies whether the **Automatic** button is at the top, before color palette.  
  
 [in] `bDrawBorder`  
 `TRUE` if the application draws a border around the color bar on the ribbon color button. Color bar displays the currently selected color. `FALSE` if the application does not draw a border  
  
##  <a name="enableotherbutton"></a>  CMFCRibbonColorButton::EnableOtherButton  
 Enables the **Other** button.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    LPCTSTR lpszToolTip=NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `lpszLabel`  
 The button's label.  
  
 `lpszToolTip`  
 The tooltip text for the **Other** button.  
  
### <a name="remarks"></a>Remarks  
 The **Other** button is the button that is displayed below the group of colors. When the user clicks the **Other** button, it displays a color dialog.  
  
##  <a name="getautomaticcolor"></a>  CMFCRibbonColorButton::GetAutomaticColor  
 Retrieves the current automatic-button color.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Return Value  
 An RGB color value that represents the current automatic-button color.  
  
### <a name="remarks"></a>Remarks  
 The automatic-button color is set by the `colorAutomatic` parameter passed to the `CMFCRibbonColorButton::EnableAutomaticButton` method.  
  
##  <a name="getcolor"></a>  CMFCRibbonColorButton::GetColor  
 Returns the currently selected color.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The color selected by clicking the button.  
  
##  <a name="getcolorboxsize"></a>  CMFCRibbonColorButton::GetColorBoxSize  
 Returns the size of the color elements that appear on the color bar.  
  
```  
CSize GetColorBoxSize() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The size of the color buttons in the drop-down color palette.  
  
##  <a name="getcolumns"></a>  CMFCRibbonColorButton::GetColumns  
 Gets the number of items in a row of the ribbon color button’s gallery display.  
  
```  
int GetColumns() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Returns the number of icons in each row.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gethighlightedcolor"></a>  CMFCRibbonColorButton::GetHighlightedColor  
 Returns the color of the currently selected element on the pop-up color palette.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The color of currently selected element on the pop-up color palette.  
  
##  <a name="removeallcolorgroups"></a>  CMFCRibbonColorButton::RemoveAllColorGroups  
 Removes all color groups from the regular color area.  
  
```  
void RemoveAllColorGroups();
```  
  
##  <a name="setcolor"></a>  CMFCRibbonColorButton::SetColor  
 Selects a color from the regular color area.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `color`  
 A color to set.  
  
##  <a name="setcolorboxsize"></a>  CMFCRibbonColorButton::SetColorBoxSize  
 Sets the size of all the color elements that appear on the color bar.  
  
```  
void SetColorBoxSize(CSize sizeBox);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `sizeBox`  
 The new size of the color buttons in the color palette.  
  
##  <a name="setcolorname"></a>  CMFCRibbonColorButton::SetColorName  
 Sets a new name for a specified color.  
  
```  
static void __stdcall SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `color`  
 The RGB value of a color.  
  
 [in] `strName`  
 The new name for the specified color.  
  
### <a name="remarks"></a>Remarks  
 Because it calls `CMFCColorBar::SetColorName`, this method changes the name of the specified color in all `CMFCColorBar` objects in your application.  
  
##  <a name="setcolumns"></a>  CMFCRibbonColorButton::SetColumns  
 Sets the number of columns displayed in the table of colors that is presented to the user during the user's color selection process.  
  
```  
void SetColumns(int nColumns);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `nColumns`  
 The number of color icons to display in each row.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setdocumentcolors"></a>  CMFCRibbonColorButton::SetDocumentColors  
 Specifies a list of RGB values to display in the document color area.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `lpszLabel`  
 The text to be displayed with the document colors.  
  
 [in] `lstColors`  
 A reference to a list of RGB values.  
  
##  <a name="setpalette"></a>  CMFCRibbonColorButton::SetPalette  
 Specifies the standard colors to display in the color table that the color button displays.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pPalette`  
 A pointer to a color palette.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="updatecolor"></a>  CMFCRibbonColorButton::UpdateColor  
 Called by the framework when the user selects a color from the color table displayed when the user clicks the color button.  
  
```  
void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `color`  
 A color selected by the user.  
  
### <a name="remarks"></a>Remarks  
 The `CMFCRibbonColorButton::UpdateColor` method changes the currently selected button's color and notifies its parent by sending a `WM_COMMAND` message with a `BN_CLICKED` standard notification. Use the [CMFCRibbonColorButton::GetColor](#getcolor) method to retrieve the selected color.  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery Class](../../mfc/reference/cmfcribbongallery-class.md)

