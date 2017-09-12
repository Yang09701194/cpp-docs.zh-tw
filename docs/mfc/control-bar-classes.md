---
title: Control Bar Classes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.control
dev_langs:
- C++
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
caps.latest.revision: 9
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
ms.translationtype: HT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: b798583c9848ca035fbbea45d9a58b638caf137d
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="control-bar-classes"></a>Control Bar Classes
Control bars are attached to a frame window. They contain buttons, status panes, or a dialog template. Free-floating control bars, also called tool palettes, are implemented by attaching them to a [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) object.  
  
## <a name="framework-control-bars"></a>Framework Control Bars  
 These control bars are an integral part of the MFC framework. They are easier to use and more powerful than the Windows control bars because they are integrated with the framework. Most MFC applications use these control bars rather than the Windows control bars.  
  
 [CControlBar](../mfc/reference/ccontrolbar-class.md)  
 The base class for MFC control bars listed in this section. A control bar is a window aligned to the edge of a frame window. The control bar contains either `HWND`-based child controls or controls not based on an `HWND`, such as toolbar buttons.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 A control bar that is based on a dialog box template.  
  
 [CReBar](../mfc/reference/crebar-class.md)  
 Supports a toolbar that can contain additional child windows in the form of controls.  
  
 [CToolBar](../mfc/reference/ctoolbar-class.md)  
 Toolbar control windows that contain bitmap command buttons not based on an `HWND`. Most MFC applications use this class rather than `CToolBarCtrl`.  
  
 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
 The base class for status-bar control windows. Most MFC applications use this class rather than `CStatusBarCtrl`.  
  
## <a name="windows-control-bars"></a>Windows Control Bars  
 These control bars are thin wrappers for the corresponding Windows controls. Because they are not integrated with the framework, they are harder to use than the control bars previously listed. Most MFC applications use the control bars previously listed.  
  
 [CRebarCtrl](../mfc/reference/crebarctrl-class.md)  
 Implements the internal control of the `CRebar` object.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 A horizontal window, usually divided into panes, in which an application can display status information.  
  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Provides the functionality of the Windows toolbar common control.  
  
## <a name="related-classes"></a>Related Classes  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 A small pop-up window that displays a single line of text describing the purpose of a tool in an application.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Handles persistent storage of docking state data for control bars.  
  
## <a name="see-also"></a>See Also  
 [Class Overview](../mfc/class-library-overview.md)


