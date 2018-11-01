---
title: CGlobalUtils 類別
ms.date: 10/18/2018
f1_keywords:
- CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils::AdjustRectToWorkArea
- AFXGLOBALUTILS/CGlobalUtils::CalcExpectedDockedRect
- AFXGLOBALUTILS/CGlobalUtils::CanBeAttached
- AFXGLOBALUTILS/CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd
- AFXGLOBALUTILS/CGlobalUtils::CheckAlignment
- AFXGLOBALUTILS/CGlobalUtils::CyFromString
- AFXGLOBALUTILS/CGlobalUtils::DecimalFromString
- AFXGLOBALUTILS/CGlobalUtils::FlipRect
- AFXGLOBALUTILS/CGlobalUtils::ForceAdjustLayout
- AFXGLOBALUTILS/CGlobalUtils::GetDockingManager
- AFXGLOBALUTILS/CGlobalUtils::GetOppositeAlignment
- AFXGLOBALUTILS/CGlobalUtils::GetPaneAndAlignFromPoint
- AFXGLOBALUTILS/CGlobalUtils::GetWndIcon
- AFXGLOBALUTILS/CGlobalUtils::SetNewParent
- AFXGLOBALUTILS/CGlobalUtils::StringFromCy
- AFXGLOBALUTILS/CGlobalUtils::StringFromDecimal
helpviewer_keywords:
- CGlobalUtils [MFC], AdjustRectToWorkArea
- CGlobalUtils [MFC], CalcExpectedDockedRect
- CGlobalUtils [MFC], CanBeAttached
- CGlobalUtils [MFC], CanPaneBeInFloatingMultiPaneFrameWnd
- CGlobalUtils [MFC], CheckAlignment
- CGlobalUtils [MFC], CyFromString
- CGlobalUtils [MFC], DecimalFromString
- CGlobalUtils [MFC], FlipRect
- CGlobalUtils [MFC], ForceAdjustLayout
- CGlobalUtils [MFC], GetDockingManager
- CGlobalUtils [MFC], GetOppositeAlignment
- CGlobalUtils [MFC], GetPaneAndAlignFromPoint
- CGlobalUtils [MFC], GetWndIcon
- CGlobalUtils [MFC], SetNewParent
- CGlobalUtils [MFC], StringFromCy
- CGlobalUtils [MFC], StringFromDecimal
ms.assetid: 2c5bd1a6-f80c-4e79-a476-b4ceebabfb2f
ms.openlocfilehash: bd382a7f0143d1dce75815430741ef58cee0f8c0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643309"
---
# <a name="cglobalutils-class"></a>CGlobalUtils 類別

如需詳細資訊，請參閱中的原始程式碼**VC\\atlmfc\\src\\mfc** Visual Studio 安裝資料夾。

## <a name="syntax"></a>語法

```
class CGlobalUtils
```

## <a name="members"></a>成員

### <a name="public-methods"></a>公用方法

|名稱|描述|
|----------|-----------------|
|[CGlobalUtils::AdjustRectToWorkArea](#adjustrecttoworkarea)||
|[CGlobalUtils::CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CGlobalUtils::CanBeAttached](#canbeattached)||
|[CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd](#canpanebeinfloatingmultipaneframewnd)||
|[CGlobalUtils::CheckAlignment](#checkalignment)||
|[CGlobalUtils::CyFromString](#cyfromstring)||
|[CGlobalUtils::DecimalFromString](#decimalfromstring)||
|[CGlobalUtils::FlipRect](#fliprect)||
|[CGlobalUtils::ForceAdjustLayout](#forceadjustlayout)||
|[CGlobalUtils::GetDockingManager](#getdockingmanager)||
|[CGlobalUtils::GetOppositeAlignment](#getoppositealignment)||
|[CGlobalUtils::GetPaneAndAlignFromPoint](#getpaneandalignfrompoint)||
|[CGlobalUtils::GetWndIcon](#getwndicon)||
|[CGlobalUtils::SetNewParent](#setnewparent)||
|[CGlobalUtils::StringFromCy](#stringfromcy)||
|[CGlobalUtils::StringFromDecimal](#stringfromdecimal)||

## <a name="remarks"></a>備註

## <a name="inheritance-hierarchy"></a>繼承階層

[CGlobalUtils](../../mfc/reference/cglobalutils-class.md)

## <a name="requirements"></a>需求

**標頭：** afxglobalutils.h

##  <a name="adjustrecttoworkarea"></a>  CGlobalUtils::AdjustRectToWorkArea

```
void AdjustRectToworkArea(
    CRect& rect,
    CRect* pRectDelta = NULL);
```

### <a name="parameters"></a>參數

[in、 out]*rect*<br/>
[in]*pRectDelta*<br/>

### <a name="remarks"></a>備註

##  <a name="calcexpecteddockedrect"></a>  CGlobalUtils::CalcExpectedDockedRect

```
void CalcExpectedDockedRect(
    CPaneContainerManager& barContainerManager,
    CWnd* pWndTodock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>參數

[in]*barContainerManager*<br/>

[in]*pWndTodock*<br/>

[in]*ptMouse*<br/>

[out]*rectResult*<br/>

[out]*bDrawTab*<br/>

[out]*ppTargetBar*<br/>

### <a name="remarks"></a>備註

##  <a name="canbeattached"></a>  CGlobalUtils::CanBeAttached

```
BOOL CanBeAttached(CWnd* pWnd) const;
```

### <a name="parameters"></a>參數

[in]*pWnd*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

##  <a name="canpanebeinfloatingmultipaneframewnd"></a>  CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd

```
BOOL CanPaneBeInFloatingMultiPaneFrameWnd(CWnd* pWnd) const;
```

### <a name="parameters"></a>參數

[in]*pWnd*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

##  <a name="checkalignment"></a>  CGlobalUtils::CheckAlignment

```
BOOL CheckAlignment(
    CPoint point,
    CBasePane* pBar,
    int nSensitivity,
    const CDockingManager* pDockManager,
    BOOL bOuterEdge,
    DWORD& dwAlignment,
    DWORD dwEnabledDockBars = CBRS_ALIGN_ANY,
    LPCRECT lpRectBounds = NULL) const;
```

### <a name="parameters"></a>參數

[in]*點*<br/>

[in]*pBar*<br/>

[in]*nSensitivity*<br/>

[in]*pDockManager*<br/>

[in]*bOuterEdge*<br/>

[out]*dwAlignment*<br/>

[in]*dwEnabledDockBars*<br/>

[in]*lpRectBounds*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

##  <a name="cyfromstring"></a>  CGlobalUtils::CyFromString

```
BOOL CyFromString(
    CY& cy,
    LPCTSTR psz);
```

### <a name="parameters"></a>參數

[out]*cy*<br/>

[in]*psz*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

##  <a name="decimalfromstring"></a>  CGlobalUtils::DecimalFromString

```
BOOL DecimalFromString(
    DECIMAL& decimal,
    LPCTSTR psz);
```

### <a name="parameters"></a>參數

[out]*十進位*<br/>

[in]*psz*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

##  <a name="fliprect"></a>  CGlobalUtils::FlipRect

```
void FlipRect(
    CRect& rect,
    int nDegrees);
```

### <a name="parameters"></a>參數

[in、 out]*rect*<br/>
[in]*nDegrees*<br/>

### <a name="remarks"></a>備註

##  <a name="forceadjustlayout"></a>  CGlobalUtils::ForceAdjustLayout

```
void ForceAdjustLayout(
    CDockingManager* pDockManager,
    BOOL bForce = FALSE,
    BOOL bForceInvisible = FALSE);
```

### <a name="parameters"></a>參數

[in、 out]*pDockManager*<br/>

[in]*bForce*<br/>

[in]*bForceInvisible*<br/>

### <a name="remarks"></a>備註

##  <a name="getdockingmanager"></a>  CGlobalUtils::GetDockingManager

```
CDockingManager* GetDockingManager(CWnd* pWnd);
```

### <a name="parameters"></a>參數

[in]*pWnd*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

##  <a name="getoppositealignment"></a>  CGlobalUtils::GetOppositeAlignment

```
DWORD GetOppositeAlignment(DWORD dwAlign);
```

### <a name="parameters"></a>參數

[in]*dwAlign*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

##  <a name="getpaneandalignfrompoint"></a>  CGlobalUtils::GetPaneAndAlignFromPoint

```
BOOL GetPaneAndAlignFromPoint(
    CPaneContainerManager& barContainerManager,
    CPoint pt,
    CDockablePane** ppTargetControlBar,
    DWORD& dwAlignment,
    BOOL& bTabArea,
    BOOL& bCaption);
```

### <a name="parameters"></a>參數

[in]*barContainerManager*<br/>

[in]*pt*<br/>

[out]*ppTargetControlBar*<br/>

[out]*dwAlignment*<br/>

[out]*bTabArea*<br/>

[out]*bCaption*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

##  <a name="getwndicon"></a>  CGlobalUtils::GetWndIcon

```
HICON GetWndIcon(CWnd* pWnd);
```

### <a name="parameters"></a>參數

[in]*pWnd*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

##  <a name="setnewparent"></a>  CGlobalUtils::SetNewParent

```
void SetNewParent(
    CObList& lstControlBars,
    CWnd* pNewParent,
    BOOL bCheckVisibility = TRUE);
```

### <a name="parameters"></a>參數

[in]*lstControlBars*<br/>

[in]*pNewParent*<br/>

[in]*bCheckVisibility*<br/>

### <a name="remarks"></a>備註

##  <a name="stringfromcy"></a>  CGlobalUtils::StringFromCy

```
BOOL StringFromCy(
    CString& str,
    CY& cy);
```

### <a name="parameters"></a>參數

[out]*str*<br/>

[in]*cy*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

##  <a name="stringfromdecimal"></a>  CGlobalUtils::StringFromDecimal

```
BOOL StringFromDecimal(
    CString& str,
    DECIMAL& decimal);
```

### <a name="parameters"></a>參數

[out]*str*<br/>

[in]*十進位*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

## <a name="see-also"></a>另請參閱

[階層架構圖表](../../mfc/hierarchy-chart.md)<br/>
[類別](../../mfc/reference/mfc-classes.md)
