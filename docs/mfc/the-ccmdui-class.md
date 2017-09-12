---
title: The CCmdUI Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCmdUI
dev_langs:
- C++
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
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
ms.openlocfilehash: 85c95a24e5c42e0d90d6f3b90ae22f10eec18f8d
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="the-ccmdui-class"></a>The CCmdUI Class
When it routes an update command to its handler, the framework passes the handler a pointer to a `CCmdUI` object (or to an object of a `CCmdUI`-derived class). This object represents the menu item or toolbar button or other user-interface object that generated the command. The update handler calls member functions of the `CCmdUI` structure through the pointer to update the user-interface object. For example, here is an update handler for the Clear All menu item:  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]  
  
 This handler calls the **Enable** member function of an object with access to the menu item. **Enable** makes the item available for use.  
  
## <a name="see-also"></a>See Also  
 [How to: Update User-Interface Objects](../mfc/how-to-update-user-interface-objects.md)


