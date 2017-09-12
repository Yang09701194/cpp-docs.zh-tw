---
title: Working with a Tab Control | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CTabCtrl class [MFC], using
- tab controls [MFC], working with
- tab controls [MFC], using
ms.assetid: 819488e3-4944-44b7-9483-195edb8e0aed
caps.latest.revision: 10
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
ms.openlocfilehash: 3ab06d599c81b9c91b7c6e5aa87013daa1c78506
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="working-with-a-tab-control"></a>Working with a Tab Control
The easiest way to use a tab control ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) is by adding it to a dialog template resource with the dialog editor. You can also use a tab control by itself. MFC calls **InitCommonControls** for you. The key tasks are as follows:  
  
-   [Creating the tab control](../mfc/creating-the-tab-control.md)  
  
-   [Adding tabs to a tab control](../mfc/adding-tabs-to-a-tab-control.md)  
  
-   [Processing tab control notification messages](../mfc/processing-tab-control-notification-messages.md)  
  
 If the tab control object is embedded in a parent view or dialog class, the control is destroyed when the parent is destroyed.  
  
## <a name="see-also"></a>See Also  
 [Using CTabCtrl](../mfc/using-ctabctrl.md)   
 [Controls](../mfc/controls-mfc.md)


