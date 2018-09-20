---
title: WM_ 訊息： T-Z |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ON_WM_TCARD
- ON_WM_WININICHANGE
- ON_WM_VSCROLLCLIPBOARD
- ON_WM_VSCROLL
- ON_WM_WINDOWPOSCHANGED
- ON_WM_TIMECHANGE
- ON_WM_TIMER
- ON_WM_VKEYTOITEM
- ON_WM_WINDOWPOSCHANGING
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_VSCROLLCLIPBOARD [MFC]
- ON_WM_WININICHANGE [MFC]
- ON_WM_WINDOWPOSCHANGED [MFC]
- ON_WM_TCARD [MFC]
- ON_WM_TIMECHANGE [MFC]
- ON_WM_TIMER [MFC]
- WM_ messages [MFC]
- ON_WM_WINDOWPOSCHANGING [MFC]
- ON_WM_VKEYTOITEM [MFC]
- ON_WM_VSCROLL
ms.assetid: c528bb2e-ddb5-4da6-b652-432a387408b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2daf2198d963f24c01e30a16f61d473ab76e3dce
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435788"
---
# <a name="wm-messages-t---z"></a>WM_ 訊息：T - Z

下列的對應項目對應至函式原型：

|對應項目|函式原型|
|---------------|------------------------|
|ON_WM_TCARD()|afx_msg void [OnTCard](../../mfc/reference/cwnd-class.md#ontcard)UINT (DWORD）;|
|ON_WM_TIMECHANGE()|afx_msg void [OnTimeChange](../../mfc/reference/cwnd-class.md#ontimechange)（);|
|ON_WM_TIMER()|afx_msg void [OnTimer](../../mfc/reference/cwnd-class.md#ontimer)(UINT_PTR);|
|ON_WM_UNICHAR()|afx_msg void [OnUniChar](../../mfc/reference/cwnd-class.md#onunichar)（UINT，UINT，UINT）;|
|ON_WM_UNINITMENUPOPUP()|afx_msg void [OnUnInitMenuPopup](../../mfc/reference/cwnd-class.md#onuninitmenupopup)（CMenu *，UINT）;|
|ON_WM_USERCHANGED()|afx_msg void [OnUserChanged](../../mfc/reference/cwnd-class.md#onuserchanged)（);|
|ON_WM_VKEYTOITEM()|afx_msg int [OnVKeyToItem](../../mfc/reference/cwnd-class.md#onvkeytoitem)（UINT，CWnd *，UINT）;|
|ON_WM_VSCROLL()|afx_msg void [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)UINT，UINT (CWnd *）;|
|ON_WM_VSCROLLCLIPBOARD()|afx_msg void [OnVScrollClipboard](../../mfc/reference/cwnd-class.md#onvscrollclipboard)（CWnd *，UINT，UINT）;|
|ON_WM_WINDOWPOSCHANGED()|afx_msg void [OnWindowPosChanged](../../mfc/reference/cwnd-class.md#onwindowposchanged)（WINDOWPOS *;）|
|ON_WM_WINDOWPOSCHANGING()|afx_msg void [OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)（WINDOWPOS *;）|
|ON_WM_WININICHANGE()|afx_msg void [OnWinIniChange](../../mfc/reference/cwnd-class.md#onwininichange)(LPSTR);|
|ON_WM_WTSSESSION_CHANGE()|afx_msg void [OnSessionChange](../../mfc/reference/cwnd-class.md#onsessionchange)（UINT，UINT）;|
|ON_WM_XBUTTONDBLCLK()|afx_msg void [OnXButtonDblClk](../../mfc/reference/cwnd-class.md#onxbuttondblclk)（UINT，UINT，CPoint）;|
|ON_WM_XBUTTONDOWN()|afx_msg void [OnXButtonDown](../../mfc/reference/cwnd-class.md#onxbuttondown)（UINT，UINT，CPoint）;|
|ON_WM_XBUTTONUP()|afx_msg void [OnXButtonUp](../../mfc/reference/cwnd-class.md#onxbuttonup)（UINT，UINT，CPoint）;|

## <a name="see-also"></a>另請參閱

[訊息對應](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ 訊息的處理常式](../../mfc/reference/handlers-for-wm-messages.md)

