---
title: List-Box Styles | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LBS_STANDARD
- LBS_NODATA
- LBS_OWNERDRAWVARIABLE
- LBS_EXTENDEDSEL
- LBS_USETABSTOPS
- LBS_WANTKEYBOARDINPUT
- LBS_NOTIFY
- LBS_DISABLENOSCROLL
- LBS_HASSTRINGS
- LBS_NOREDRAW
- LBS_NOSEL
- LBS_NOINTEGRALHEIGHT
- LBS_MULTICOLUMN
- LBS_SORT
- LBS_MULTIPLESEL
- LBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- LBS_NOSEL constant [MFC]
- LBS_NOREDRAW constant [MFC]
- LBS_HASSTRINGS constant [MFC]
- LBS_OWNERDRAWFIXED constant [MFC]
- LBS_WANTKEYBOARDINPUT constant [MFC]
- LBS_STANDARD constant [MFC]
- LBS_MULTIPLESEL constant [MFC]
- LBS_OWNERDRAWVARIABLE constant [MFC]
- LBS_DISABLENOSCROLL constant [MFC]
- LBS_NODATA constant [MFC]
- list boxes [MFC], styles
- LBS_EXTENDEDSEL constant [MFC]
- LBS_MULTICOLUMN constant [MFC]
- LBS_NOTIFY constant [MFC]
- LBS_USETABSTOPS constant [MFC]
- LBS_NOINTEGRALHEIGHT constant [MFC]
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
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
ms.openlocfilehash: cad7dce447e41b72116dc8317f7a05649cd34e76
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="list-box-styles"></a>List-Box Styles
-   **LBS_DISABLENOSCROLL** The list box shows a disabled vertical scroll bar when the list box does not contain enough items to scroll. Without this style, the scroll bar is hidden when the list box does not contain enough items.  
  
-   **LBS_EXTENDEDSEL** The user can select multiple items using the SHIFT key and the mouse or special key combinations.  
  
-   **LBS_HASSTRINGS** Specifies an owner-draw list box that contains items consisting of strings. The list box maintains the memory and pointers for the strings so the application can use the `GetText` member function to retrieve the text for a particular item.  
  
-   **LBS_MULTICOLUMN** Specifies a multicolumn list box that is scrolled horizontally. The `SetColumnWidth` member function sets the width of the columns.  
  
-   **LBS_MULTIPLESEL** String selection is toggled each time the user clicks or double-clicks the string. Any number of strings can be selected.  
  
-   **LBS_NODATA** Specifies a no-data list box. Specify this style when the count of items in the list box will exceed one thousand. A no-data list box must also have the **LBS_OWNERDRAWFIXED** style, but must not have the **LBS_SORT** or **LBS_HASSTRINGS** style.  
  
     A no-data list box resembles an owner-drawn list box except that it contains no string or bitmap data for an item. Commands to add, insert, or delete an item always ignore any given item data; requests to find a string within the list box always fail. The system sends the `WM_DRAWITEM` message to the owner window when an item must be drawn. The itemID member of the `DRAWITEMSTRUCT` structure passed with the `WM_DRAWITEM` message specifies the line number of the item to be drawn. A no-data list box does not send a `WM_DELETEITEM` message.  
  
-   **LBS_NOINTEGRALHEIGHT** The size of the list box is exactly the size specified by the application when it created the list box. Usually, Windows sizes a list box so that the list box does not display partial items.  
  
-   **LBS_NOREDRAW** List-box display is not updated when changes are made. This style can be changed at any time by sending a **WM_SETREDRAW** message.  
  
-   **LBS_NOSEL** Specifies that the list box contains items that can be viewed but not selected.  
  
-   **LBS_NOTIFY** Parent window receives an input message whenever the user clicks or double-clicks a string.  
  
-   **LBS_OWNERDRAWFIXED** The owner of the list box is responsible for drawing its contents; the items in the list box are the same height.  
  
-   **LBS_OWNERDRAWVARIABLE** The owner of the list box is responsible for drawing its contents; the items in the list box are variable in height.  
  
-   **LBS_SORT** Strings in the list box are sorted alphabetically.  
  
-   **LBS_STANDARD** Strings in the list box are sorted alphabetically, and the parent window receives an input message whenever the user clicks or double-clicks a string. The list box contains borders on all sides.  
  
-   **LBS_USETABSTOPS** Allows a list box to recognize and expand tab characters when drawing its strings. The default tab positions are 32 dialog units. (A dialog unit is a horizontal or vertical distance. One horizontal dialog unit is equal to one-fourth of the current dialog base width unit. The dialog base units are computed based on the height and width of the current system font. The **GetDialogBaseUnits** Windows function returns the current dialog base units in pixels.) This style should not be used with **LBS_OWNERDRAWFIXED**.  
  
-   **LBS_WANTKEYBOARDINPUT** The owner of the list box receives `WM_VKEYTOITEM` or `WM_CHARTOITEM` messages whenever the user presses a key while the list box has input focus. This allows an application to perform special processing on the keyboard input.  
  
## <a name="see-also"></a>See Also  
 [Styles Used by MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [List Box Styles](http://msdn.microsoft.com/library/windows/desktop/bb775149)


