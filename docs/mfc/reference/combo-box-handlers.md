---
title: Combo Box Handlers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_CBN_KILLFOCUS
- ON_CBN_ERRSPACE
- ON_CBN_EDITCHANGE
- ON_CBN_CLOSEUP
- ON_CBN_DBLCLK
- ON_CBN_EDITUPDATE
- ON_CBN_DROPDOWN
- ON_CBN_SELENDOK
- ON_CBN_SELCHANGE
- ON_CBN_SETFOCUS
- ON_CBN_SELENDCANCEL
dev_langs:
- C++
helpviewer_keywords:
- ON_CBN_CLOSEUP
- ON_CBN_SETFOCUS
- ON_CBN_DBLCLK
- ON_CBN_SELENDCANCEL
- ON_CBN_DROPDOWN
- ON_CBN_EDITUPDATE
- ON_CBN_KILLFOCUS
- combo boxes [MFC], handlers
- ON_CBN_EDITCHANGE
- ON_CBN_ERRSPACE
- ON_CBN_SELENDOK
- ON_CBN_SELCHANGE
ms.assetid: 7f092412-01b7-4242-95ec-41ba506b9d71
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
ms.openlocfilehash: 6b08c91d092992bf65c233ef14bc78234a7a621e
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="combo-box-handlers"></a>Combo Box Handlers
The following map entries correspond to the function prototypes.  
  
|Map entry|Function prototype|  
|---------------|------------------------|  
|ON_CBN_CLOSEUP( \<id>, \<memberFxn> )|afx_msg void memberFxn( )|  
|ON_CBN_DBLCLK( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_CBN_DROPDOWN( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_CBN_EDITCHANGE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_CBN_EDITUPDATE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_CBN_ERRSPACE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_CBN_KILLFOCUS( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_CBN_SELCHANGE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_CBN_SELENDCANCEL( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_CBN_SELENDOK( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
|ON_CBN_SETFOCUS( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|  
  
## <a name="see-also"></a>See Also  
 [Message Maps](../../mfc/reference/message-maps-mfc.md)


