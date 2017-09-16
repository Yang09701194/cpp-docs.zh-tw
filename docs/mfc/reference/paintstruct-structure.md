---
title: PAINTSTRUCT Structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: 12
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
ms.openlocfilehash: b27dcb247437b37631e306b171c4201142c33cae
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="paintstruct-structure"></a>PAINTSTRUCT Structure
The `PAINTSTRUCT` structure contains information that can be used to paint the client area of a window.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagPAINTSTRUCT {  
    HDC hdc;  
    BOOL fErase;  
    RECT rcPaint;  
    BOOL fRestore;  
    BOOL fIncUpdate;  
    BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### <a name="parameters"></a>Parameters  
 *hdc*  
 Identifies the display context to be used for painting.  
  
 *fErase*  
 Specifies whether the background needs to be redrawn. It is not 0 if the application should redraw the background. The application is responsible for drawing the background if a Windows window-class is created without a background brush (see the description of the **hbrBackground** member of the [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) structure in the Windows SDK).  
  
 *rcPaint*  
 Specifies the upper left and lower right corners of the rectangle in which the painting is requested.  
  
 *fRestore*  
 Reserved member. It is used internally by Windows.  
  
 *fIncUpdate*  
 Reserved member. It is used internally by Windows.  
  
 *rgbReserved[16]*  
 Reserved member. A reserved block of memory used internally by Windows.  
  
## <a name="requirements"></a>Requirements  
 **Header:** winuser.h  
  
## <a name="see-also"></a>See Also  
 [Structures, Styles, Callbacks, and Message Maps](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)


