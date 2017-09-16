---
title: CMFCBaseVisualManager Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawCheckBox
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboBorder
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboDropButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawPushButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawRadioButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawStatusBarProgress
- AFXVISUALMANAGER/CMFCBaseVisualManager::FillReBarPane
- AFXVISUALMANAGER/CMFCBaseVisualManager::GetStandardWindowsTheme
- AFXVISUALMANAGER/CMFCBaseVisualManager::CleanUpThemes
- AFXVISUALMANAGER/CMFCBaseVisualManager::UpdateSystemColors
dev_langs:
- C++
helpviewer_keywords:
- CMFCBaseVisualManager [MFC], CMFCBaseVisualManager
- CMFCBaseVisualManager [MFC], DrawCheckBox
- CMFCBaseVisualManager [MFC], DrawComboBorder
- CMFCBaseVisualManager [MFC], DrawComboDropButton
- CMFCBaseVisualManager [MFC], DrawPushButton
- CMFCBaseVisualManager [MFC], DrawRadioButton
- CMFCBaseVisualManager [MFC], DrawStatusBarProgress
- CMFCBaseVisualManager [MFC], FillReBarPane
- CMFCBaseVisualManager [MFC], GetStandardWindowsTheme
- CMFCBaseVisualManager [MFC], CleanUpThemes
- CMFCBaseVisualManager [MFC], UpdateSystemColors
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
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
ms.openlocfilehash: 603a805d9206862d6893fd36b1815d1d3b6da0e1
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager Class
A layer between derived visual managers and the Windows Theme API.  
  
 `CMFCBaseVisualManager` loads UxTheme.dll, if available, and manages access to Windows Theme API methods.  
  
 This class is for internal use only.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|Constructs and initializes a `CMFCBaseVisualManager` object.|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Destructor.|  
  
### <a name="public-methods"></a>Public Methods  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|Draws a check box control by using the current Windows theme.|  
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|Draws a combo box border using the current Windows theme.|  
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|Draws a combo box drop-down button using the current Windows theme.|  
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|Draws a push button using the current Windows theme.|  
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|Draws a radio button control by using the current Windows theme.|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|Draws a progress bar on a status bar control ( [CMFCStatusBar Class](../../mfc/reference/cmfcstatusbar-class.md)) using the current Windows theme.|  
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|Fills the background of the rebar control by using the current Windows theme.|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|Gets the current Windows theme.|  
  
### <a name="protected-methods"></a>Protected Methods  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|Calls `CloseThemeData` for all handles obtained in `UpdateSystemColors`.|  
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|Calls `OpenThemeData` to obtain handles for drawing various controls: windows, toolbars, buttons, and so on.|  
  
## <a name="remarks"></a>Remarks  
 You do not have to instantiate objects of this class directly.  
  
 Because it is a base class for all visual managers, you can just call [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance), obtain a pointer to the current Visual Manager, and access the methods for `CMFCBaseVisualManager` using that pointer. However, if you have to display a control by using the current Windows theme, it is better to use the `CMFCVisualManagerWindows` interface.  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxvisualmanager.h  
  
##  <a name="cleanupthemes"></a>  CMFCBaseVisualManager::CleanUpThemes  
 Calls `CloseThemeData` for all handles obtained in `UpdateSystemColors`.  
  
```  
void CleanUpThemes();
```  
  
### <a name="remarks"></a>Remarks  
 For internal use only.  
  
##  <a name="cmfcbasevisualmanager"></a>  CMFCBaseVisualManager::CMFCBaseVisualManager  
 Constructs and initializes a `CMFCBaseVisualManager` object.  
  
```  
CMFCBaseVisualManager();
```  
  
##  <a name="drawcheckbox"></a>  CMFCBaseVisualManager::DrawCheckBox  
 Draws a check box control by using the current Windows theme.  
  
```  
virtual BOOL DrawCheckBox(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    int nState,   
    BOOL bEnabled,   
    BOOL bPressed);

);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 A pointer to a device context  
  
 [in] `rect`  
 The bounding rectangle of the check box.  
  
 [in] `bHighlighted`  
 Specifies whether the check box is highlighted.  
  
 [in] `nState`  
 0 for unchecked, 1 for checked normal,  
  
 2 for mixed normal.  
  
 [in] `bEnabled`  
 Specifies whether the check box is enabled.  
  
 [in] `bPressed`  
 Specifies whether the check box is pressed.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if Theme API is enabled; otherwise `FALSE`.  
  
### <a name="remarks"></a>Remarks  
 The values of `nState` correspond to the following check box styles.  
  
|nState|Check box style|  
|------------|---------------------|  
|0|CBS_UNCHECKEDNORMAL|  
|1|CBS_CHECKEDNORMAL|  
|2|CBS_MIXEDNORMAL|  
  
##  <a name="drawcomboborder"></a>  CMFCBaseVisualManager::DrawComboBorder  
 Draws the combo box border using the current Windows theme.  
  
```  
virtual BOOL DrawComboBorder(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 A pointer to a device context.  
  
 [in] `rect`  
 Bounding rectangle of the combo box border.  
  
 [in] `bDisabled`  
 Specifies whether the combo box border is disabled.  
  
 [in] `bIsDropped`  
 Specifies whether the combo box border is dropped down.  
  
 [in] `bIsHighlighted`  
 Specifies whether the combo box border is highlighted.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if Theme API is enabled; otherwise `FALSE`.  
  
##  <a name="drawcombodropbutton"></a>  CMFCBaseVisualManager::DrawComboDropButton  
 Draws a combo box drop-down button using the current Windows theme.  
  
```  
virtual BOOL DrawComboDropButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pDC`|A pointer to a device context.|  
|[in] `rect`|The bounding rectangle of the combo box drop-down button.|  
|[in] `bDisabled`|Specifies whether the combo box drop-down button is disabled.|  
|[in] `bIsDropped`|Specifies whether the combo box drop-down button is dropped down.|  
|[in] `bIsHighlighted`|Specifies whether the combo box drop-down button is highlighted.|  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if Theme API is enabled; otherwise `FALSE`.  
  
##  <a name="drawpushbutton"></a>  CMFCBaseVisualManager::DrawPushButton  
 Draws a push button using the current Windows theme.  
  
```  
virtual BOOL DrawPushButton(
    CDC* pDC,   
    CRect rect,   
    CMFCButton* pButton,   
    UINT uiState);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 A pointer to a device context.  
  
 [in] `rect`  
 The bounding rectangle of the push button.  
  
 [in] `pButton`  
 A pointer to the [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md) object to draw.  
  
 [in] `uiState`  
 Ignored. The state is taken from `pButton`.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if Theme API is enabled; otherwise `FALSE`.  
  
##  <a name="drawradiobutton"></a>  CMFCBaseVisualManager::DrawRadioButton  
 Draws a radio button control by using the current Windows theme.  
  
```  
virtual BOOL DrawRadioButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    BOOL bChecked,   
    BOOL bEnabled,   
    BOOL bPressed);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 A pointer to a device context.  
  
 [in] `rect`  
 The bounding rectangle of the radio button.  
  
 [in] `bHighlighted`  
 Specifies whether the radio button is highlighted.  
  
 [in] `bChecked`  
 Specifies whether the radio button is checked.  
  
 [in] `bEnabled`  
 Specifies whether the radio button is enabled.  
  
 [in] `bPressed`  
 Specifies whether the radio button is pressed.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if Theme API is enabled; otherwise `FALSE`.  
  
##  <a name="drawstatusbarprogress"></a>  CMFCBaseVisualManager::DrawStatusBarProgress  
 Draws progress bar on status bar control ( [CMFCStatusBar Class](../../mfc/reference/cmfcstatusbar-class.md)) using the current Windows theme.  
  
```  
virtual BOOL DrawStatusBarProgress(
    CDC* pDC,   
    CMFCStatusBar* pStatusBar,   
    CRect rectProgress,   
    int nProgressTotal,   
    int nProgressCurr,  
    COLORREF clrBar,   
    COLORREF clrProgressBarDest,   
    COLORREF clrProgressText,   
    BOOL bProgressText);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 A pointer to a device context.  
  
 [in] `pStatusBar`  
 A pointer to status bar. This value is ignored.  
  
 [in] `rectProgress`  
 The bounding rectangle of the progress bar in `pDC` coordinates.  
  
 [in] `nProgressTotal`  
 The total progress value.  
  
 [in] `nProgressCurr`  
 The current progress value.  
  
 [in] `clrBar`  
 The start color. `CMFCBaseVisualManager` ignores this. Derived classes can use it for color gradients.  
  
 [in] `clrProgressBarDest`  
 The end color. `CMFCBaseVisualManager` ignores this. Derived classes can use it for color gradients.  
  
 [in] `clrProgressText`  
 Progress text color. `CMFCBaseVisualManager` ignores this. The text color is defined by `afxGlobalData.clrBtnText`.  
  
 [in] `bProgressText`  
 Specifies whether to display progress text.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if Theme API is enabled; otherwise `FALSE`.  
  
##  <a name="fillrebarpane"></a>  CMFCBaseVisualManager::FillReBarPane  
 Fills the background of the rebar control by using the current Windows theme.  
  
```  
virtual void FillReBarPane(
    CDC* pDC,   
    CBasePane* pBar,   
    CRect rectClient);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 A pointer to a device context.  
  
 [in] `pBar`  
 A pointer to a pane whose background should be drawn.  
  
 [in] `rectClient`  
 The bounding rectangle of the area to be filled.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if Theme API is enabled; otherwise `FALSE`.  
  
##  <a name="getstandardwindowstheme"></a>  CMFCBaseVisualManager::GetStandardWindowsTheme  
 Gets the current Windows theme.  
  
```  
virtual WinXpTheme GetStandardWindowsTheme();
```  
  
### <a name="return-value"></a>Return Value  
 The currently selected Windows Theme color. Can be one of the following enumerated values:  
  
- `WinXpTheme_None` - there is no theme enabled.  
  
- `WinXpTheme_NonStandard` - non standard theme is selected (meaning a theme is selected, but none from the list below).  
  
- `WinXpTheme_Blue` - blue theme (Luna).  
  
- `WinXpTheme_Olive` - olive theme.  
  
- `WinXpTheme_Silver` - silver theme.  
  
##  <a name="updatesystemcolors"></a>  CMFCBaseVisualManager::UpdateSystemColors  
 Calls `OpenThemeData` to obtain handles for drawing various controls: windows, toolbars, buttons, and so on.  
  
```  
void UpdateSystemColors();
```  
  
### <a name="remarks"></a>Remarks  
 For internal use only.  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

