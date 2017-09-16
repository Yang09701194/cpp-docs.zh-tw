---
title: CD2DTextLayout Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
dev_langs:
- C++
helpviewer_keywords:
- CD2DTextLayout [MFC], CD2DTextLayout
- CD2DTextLayout [MFC], Create
- CD2DTextLayout [MFC], Destroy
- CD2DTextLayout [MFC], Get
- CD2DTextLayout [MFC], GetFontFamilyName
- CD2DTextLayout [MFC], GetLocaleName
- CD2DTextLayout [MFC], IsValid
- CD2DTextLayout [MFC], ReCreate
- CD2DTextLayout [MFC], SetFontFamilyName
- CD2DTextLayout [MFC], SetLocaleName
- CD2DTextLayout [MFC], m_pTextLayout
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
caps.latest.revision: 16
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
ms.openlocfilehash: b828d6964e4c62c3a4b1b4c14932481a7143bb98
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout Class
A wrapper for IDWriteTextLayout.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DTextLayout : public CD2DResource;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|Constructs a CD2DTextLayout object.|  
|[CD2DTextLayout::~CD2DTextLayout](#cd2dtextlayout__~cd2dtextlayout)|The destructor. Called when a D2D text layout object is being destroyed.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextLayout::Create](#create)|Creates a CD2DTextLayout. (Overrides [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DTextLayout::Destroy](#destroy)|Destroys a CD2DTextLayout object. (Overrides [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DTextLayout::Get](#get)|Returns IDWriteTextLayout interface|  
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|Copies the font family name of the text at the specified position.|  
|[CD2DTextLayout::GetLocaleName](#getlocalename)|Gets the locale name of the text at the specified position.|  
|[CD2DTextLayout::IsValid](#isvalid)|Checks resource validity (Overrides [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DTextLayout::ReCreate](#recreate)|Re-creates a CD2DTextLayout. (Overrides [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|  
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|Sets null-terminated font family name for text within a specified text range|  
|[CD2DTextLayout::SetLocaleName](#setlocalename)|Sets the locale name for text within a specified text range|  
  
### <a name="public-operators"></a>Public Operators  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextLayout::operator IDWriteTextLayout*](#operator_idwritetextlayout_star)|Returns IDWriteTextLayout interface|  
  
### <a name="protected-data-members"></a>Protected Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextLayout::m_pTextLayout](#m_ptextlayout)|A pointer to an IDWriteTextLayout.|  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcd2dtextlayout"></a>  CD2DTextLayout::~CD2DTextLayout  
 The destructor. Called when a D2D text layout object is being destroyed.  
  
```  
virtual ~CD2DTextLayout();
```  
  
##  <a name="cd2dtextlayout"></a>  CD2DTextLayout::CD2DTextLayout  
 Constructs a CD2DTextLayout object.  
  
```  
CD2DTextLayout(
    CRenderTarget* pParentTarget,  
    const CString& strText,  
    CD2DTextFormat& textFormat,  
    const CD2DSizeF& sizeMax,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameters  
 `pParentTarget`  
 A pointer to the render target.  
  
 `strText`  
 A CString object that contains the string to create a new CD2DTextLayout object from.  
  
 `textFormat`  
 A CString object that contains the format to apply to the string.  
  
 `sizeMax`  
 The size of the layout box.  
  
 `bAutoDestroy`  
 Indicates that the object will be destroyed by owner (pParentTarget).  
  
##  <a name="create"></a>  CD2DTextLayout::Create  
 Creates a CD2DTextLayout.  
  
```  
virtual HRESULT Create(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Return Value  
 If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.  
  
##  <a name="destroy"></a>  CD2DTextLayout::Destroy  
 Destroys a CD2DTextLayout object.  
  
```  
virtual void Destroy();
```  
  
##  <a name="get"></a>  CD2DTextLayout::Get  
 Returns IDWriteTextLayout interface  
  
```  
IDWriteTextLayout* Get();
```  
  
### <a name="return-value"></a>Return Value  
 Pointer to an IDWriteTextLayout interface or NULL if object is not initialized yet.  
  
##  <a name="getfontfamilyname"></a>  CD2DTextLayout::GetFontFamilyName  
 Copies the font family name of the text at the specified position.  
  
```  
CString GetFontFamilyName(
    UINT32 currentPosition,  
    DWRITE_TEXT_RANGE* textRange = NULL) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `currentPosition`  
 The position of the text to examine.  
  
 `textRange`  
 The range of text that has the same formatting as the text at the position specified by currentPosition. This means the run has the exact formatting as the position specified, including but not limited to the font family name.  
  
### <a name="return-value"></a>Return Value  
 CString object that contains the current font family name.  
  
##  <a name="getlocalename"></a>  CD2DTextLayout::GetLocaleName  
 Gets the locale name of the text at the specified position.  
  
```  
CString GetLocaleName(
    UINT32 currentPosition,  
    DWRITE_TEXT_RANGE* textRange = NULL) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `currentPosition`  
 The position of the text to inspect.  
  
 `textRange`  
 The range of text that has the same formatting as the text at the position specified by currentPosition. This means the run has the exact formatting as the position specified, including but not limited to the locale name.  
  
### <a name="return-value"></a>Return Value  
 CString object that contains the current locale name.  
  
##  <a name="isvalid"></a>  CD2DTextLayout::IsValid  
 Checks resource validity  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Return Value  
 TRUE if resource is valid; otherwise FALSE.  
  
##  <a name="m_ptextlayout"></a>  CD2DTextLayout::m_pTextLayout  
 A pointer to an IDWriteTextLayout.  
  
```  
IDWriteTextLayout* m_pTextLayout;  
```  
  
##  <a name="operator_idwritetextlayout_star"></a>  CD2DTextLayout::operator IDWriteTextLayout*  
 Returns IDWriteTextLayout interface  
  
```  
operator IDWriteTextLayout*();
```   
  
### <a name="return-value"></a>Return Value  
 Pointer to an IDWriteTextLayout interface or NULL if object is not initialized yet.  
  
##  <a name="recreate"></a>  CD2DTextLayout::ReCreate  
 Re-creates a CD2DTextLayout.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Return Value  
 If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.  
  
##  <a name="setfontfamilyname"></a>  CD2DTextLayout::SetFontFamilyName  
 Sets null-terminated font family name for text within a specified text range  
  
```  
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,  
    DWRITE_TEXT_RANGE textRange);
```  
  
### <a name="parameters"></a>Parameters  
 `pwzFontFamilyName`  
 The font family name that applies to the entire text string within the range specified by textRange  
  
 `textRange`  
 Text range to which this change applies  
  
### <a name="return-value"></a>Return Value  
 If the method succeeds, it returns TRUE. Otherwise, it returns FALSE  
  
##  <a name="setlocalename"></a>  CD2DTextLayout::SetLocaleName  
 Sets the locale name for text within a specified text range  
  
```  
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,  
    DWRITE_TEXT_RANGE textRange);
```  
  
### <a name="parameters"></a>Parameters  
 `pwzLocaleName`  
 A null-terminated locale name string  
  
 `textRange`  
 Text range to which this change applies  
  
### <a name="return-value"></a>Return Value  
 If the method succeeds, it returns TRUE. Otherwise, it returns FALSE  
  
## <a name="see-also"></a>See Also  
 [Classes](../../mfc/reference/mfc-classes.md)

