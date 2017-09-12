---
title: Edit Control Handlers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_EN_ERRSPACE
- ON_EN_UPDATE
- ON_EN_VSCROLL
- ON_EN_HSCROLL
- ON_EN_KILLFOCUS
- ON_EN_MAXTEXT
- ON_EN_SETFOCUS
- ON_EN_CHANGE
dev_langs:
- C++
helpviewer_keywords:
- ON_EN_ERRSPACE macro [MFC]
- ON_EN_SETFOCUS macro [MFC]
- ON_EN_UPDATE macro [MFC]
- ON_EN_MAXTEXT macro [MFC]
- ON_EN_CHANGE macro [MFC]
- ON_EN_HSCROLL macro [MFC]
- ON_EN_VSCROLL macro [MFC]
- ON_EN_KILLFOCUS macro [MFC]
- edit controls [MFC], edit control handlers
ms.assetid: 55b88b5e-12b5-4422-b03e-c8c2f27d095c
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
ms.translationtype: MT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 50e93478a3a4649dbd2fc0ae4e089470e1b38a8e
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="edit-control-handlers"></a>Edit Control Handlers
The following map entries correspond to the function prototype.  
  
|Map entry|Function prototype|  
|---------------|------------------------|  
|ON_EN_CHANGE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_EN_ERRSPACE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_EN_HSCROLL( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_EN_KILLFOCUS( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_EN_MAXTEXT( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_EN_SETFOCUS( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_EN_UPDATE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_EN_VSCROLL( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
  
## <a name="see-also"></a>See Also  
 [Message Maps](../../mfc/reference/message-maps-mfc.md)


