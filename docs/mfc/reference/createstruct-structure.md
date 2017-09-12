---
title: CREATESTRUCT Structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CREATESTRUCT
dev_langs:
- C++
helpviewer_keywords:
- CREATESTRUCT structure [MFC]
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: 14
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
ms.openlocfilehash: 0409e6ff80c9491ffc36b4ca7b6ecc05edfdb264
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="createstruct-structure"></a>CREATESTRUCT Structure
The `CREATESTRUCT` structure defines the initialization parameters passed to the window procedure of an application.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagCREATESTRUCT {  
    LPVOID lpCreateParams;  
    HANDLE hInstance;  
    HMENU hMenu;  
    HWND hwndParent;  
    int cy;  
    int cx;  
    int y;  
    int x;  
    LONG style;  
    LPCSTR lpszName;  
    LPCSTR lpszClass;  
    DWORD dwExStyle;  
} CREATESTRUCT;  
```  
  
#### <a name="parameters"></a>Parameters  
 `lpCreateParams`  
 Points to data to be used to create the window.  
  
 `hInstance`  
 Identifies the module-instance handle of the module that owns the new window.  
  
 `hMenu`  
 Identifies the menu to be used by the new window. If a child window, contains the integer ID.  
  
 `hwndParent`  
 Identifies the window that owns the new window. This member is **NULL** if the new window is a top-level window.  
  
 `cy`  
 Specifies the height of the new window.  
  
 `cx`  
 Specifies the width of the new window.  
  
 `y`  
 Specifies the y-coordinate of the upper left corner of the new window. Coordinates are relative to the parent window if the new window is a child window; otherwise coordinates are relative to the screen origin.  
  
 `x`  
 Specifies the x-coordinate of the upper left corner of the new window. Coordinates are relative to the parent window if the new window is a child window; otherwise coordinates are relative to the screen origin.  
  
 `style`  
 Specifies the new window's [style](../../mfc/reference/styles-used-by-mfc.md).  
  
 `lpszName`  
 Points to a null-terminated string that specifies the new window's name.  
  
 `lpszClass`  
 Points to a null-terminated string that specifies the new window's Windows class name (a [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) structure; for more information, see the Windows SDK).  
  
 `dwExStyle`  
 Specifies the [extended style](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) for the new window.  
  
## <a name="requirements"></a>Requirements  
 **Header:** winuser.h  
  
## <a name="see-also"></a>See Also  
 [Structures, Styles, Callbacks, and Message Maps](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)



