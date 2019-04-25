---
title: 編輯控制處理常式
ms.date: 11/04/2016
f1_keywords:
- ON_EN_ERRSPACE
- ON_EN_UPDATE
- ON_EN_VSCROLL
- ON_EN_HSCROLL
- ON_EN_KILLFOCUS
- ON_EN_MAXTEXT
- ON_EN_SETFOCUS
- ON_EN_CHANGE
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
ms.openlocfilehash: 53586de574fca6ab88b93444c9d571c62354cef2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322380"
---
# <a name="edit-control-handlers"></a>編輯控制處理常式

下列的對應項目會對應至函式原型。

|對應項目|函式原型|
|---------------|------------------------|
|ON_EN_CHANGE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|
|ON_EN_ERRSPACE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|
|ON_EN_HSCROLL( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|
|ON_EN_KILLFOCUS( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|
|ON_EN_MAXTEXT( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|
|ON_EN_SETFOCUS( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|
|ON_EN_UPDATE( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|
|ON_EN_VSCROLL( \<id>, \<memberFxn> )|afx_msg void memberFxn( );|

## <a name="see-also"></a>另請參閱

[訊息對應](../../mfc/reference/message-maps-mfc.md)
