---
title: Gray and Dithered Bitmap Functions | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
dev_langs:
- C++
helpviewer_keywords:
- gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
caps.latest.revision: 13
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
ms.openlocfilehash: 8263f93b440be22916dd3597c4093005255455a1
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="gray-and-dithered-bitmap-functions"></a>Gray and Dithered Bitmap Functions
**Gray Bitmap Functions**  
  
 MFC provides two functions for giving a bitmap the appearance of a disabled control.  
  
 ![Comparison of gray and original icon versions](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
|||  
|-|-|  
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Draws a gray version of a bitmap.|  
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Copies a gray version of a bitmap.|  
  
 **Dithered Bitmap Functions**  
  
 MFC also provides two functions for replacing a bitmap's background with a dithered pattern.  
  
 ![Comparison of dithered and original icon versions](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
|||  
|-|-|  
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Draws a bitmap with a dithered background.|  
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Copies a bitmap with a dithered background.|  
  
##  <a name="afxdrawgraybitmap"></a>  AfxDrawGrayBitmap  
 Draws a gray version of a bitmap.  
  
```   
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>Parameters  
 `pDC`  
 Points to the destination DC.  
  
 *x*  
 The destination x-coordinate.  
  
 *y*  
 The destination y-coordinate.  
  
 `rSrc`  
 The source bitmap.  
  
 `crBackground`  
 The new background color (typically gray, such as COLOR_MENU).  
  
### <a name="remarks"></a>Remarks  
 A bitmap drawn with `AfxDrawGrayBitmap` will have the appearance of a disabled control.  
  
 ![Comparison of gray and original icon versions](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]  

### <a name="requirements"></a>Requirements  
 **Header:** afxwin.h  

##  <a name="afxgetgraybitmap"></a>  AfxGetGrayBitmap  
 Copies a gray version of a bitmap.  
  
```   
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>Parameters  
 `rSrc`  
 The source bitmap.  
  
 `pDest`  
 The destination bitmap.  
  
 `crBackground`  
 The new background color (typically gray, such as COLOR_MENU).  
  
### <a name="remarks"></a>Remarks  
 A bitmap copied with `AfxGetGrayBitmap` will have the appearance of a disabled control.  
  
 ![Comparison of gray and original icon versions](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]  

### <a name="requirements"></a>Requirements  
 **Header:** afxwin.h  
  
##  <a name="afxdrawditheredbitmap"></a>  AfxDrawDitheredBitmap  
 Draws a bitmap, replacing its background with a dithered (checker) pattern.  
  
```   
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>Parameters  
 `pDC`  
 Points to the destination DC.  
  
 *x*  
 The destination x-coordinate.  
  
 *y*  
 The destination y-coordinate.  
  
 `rSrc`  
 The source bitmap.  
  
 `cr1`  
 One of the two dither colors, typically white.  
  
 `cr2`  
 The other dither color, typically light gray (COLOR_MENU).  
  
### <a name="remarks"></a>Remarks  
 The source bitmap is drawn on the destination DC with a two-color ( `cr1` and `cr2`) checkered pattern replacing the bitmap's background. The background of the source bitmap is defined as its white pixels and all pixels matching the color of the pixel in the upper-left corner of the bitmap.  
  
 ![Comparison of dithered and original icon versions](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]  

### <a name="requirements"></a>Requirements  
 **Header:** afxwin.h  


##  <a name="afxgetditheredbitmap"></a>  AfxGetDitheredBitmap  
 Copies a bitmap, replacing its background with a dithered (checker) pattern.  
  
```   
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>Parameters  
 `rSrc`  
 The source bitmap.  
  
 `pDest`  
 The destination bitmap.  
  
 `cr1`  
 One of the two dither colors, typically white.  
  
 `cr2`  
 The other dither color, typically light gray (COLOR_MENU).  
  
### <a name="remarks"></a>Remarks  
 The source bitmap is copied to the destination bitmap with a two-color ( `cr1` and `cr2`) checkered pattern replacing the source bitmap's background. The background of the source bitmap is defined as its white pixels and all pixels matching the color of the pixel in the upper-left corner of the bitmap.  
  
 ![Comparison of dithered and original icon versions](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]  

### <a name="requirements"></a>Requirements  
 **Header:** afxwin.h  
  
## <a name="see-also"></a>See Also  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

