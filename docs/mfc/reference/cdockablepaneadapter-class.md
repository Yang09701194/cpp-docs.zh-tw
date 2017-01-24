---
title: "CDockablePaneAdapter Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockablePaneAdapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockablePaneAdapter class"
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDockablePaneAdapter Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

提供 `CWnd` 衍生窗格的停駐支援。  
  
## 語法  
  
```  
class CDockablePaneAdapter : public CDockablePane  
```  
  
## 成員  
  
### 公用方法  
  
|名稱|描述|  
|--------|--------|  
|[CDockablePaneAdapter::GetWrappedWnd](../Topic/CDockablePaneAdapter::GetWrappedWnd.md)|傳回已包裝的視窗。|  
|[CDockablePaneAdapter::LoadState](../Topic/CDockablePaneAdapter::LoadState.md)|\(覆寫 [CDockablePane::LoadState](http://msdn.microsoft.com/zh-tw/96110136-4f46-4764-8a76-3b4abaf77917)。\)|  
|[CDockablePaneAdapter::SaveState](../Topic/CDockablePaneAdapter::SaveState.md)|\(覆寫 [CDockablePane::SaveState](http://msdn.microsoft.com/zh-tw/c5c24249-8d0d-46cb-96d9-9f5c6dc191db)。\)|  
|[CDockablePaneAdapter::SetWrappedWnd](../Topic/CDockablePaneAdapter::SetWrappedWnd.md)||  
  
## 備註  
 通常，當您使用 [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) 或 [CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md) 方法時，架構會具現化這個類別的物件。  
  
 如果您想要自訂 `CDockablePaneAdapter` 行為，只需從中衍生新類別，並使用 [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../Topic/CMFCBaseTabCtrl::SetDockingBarWrapperRTC.md)，將執行階段類別資訊設為索引標籤式視窗。  
  
## 繼承階層  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)  
  
## 需求  
 **標頭：** afxDockablePaneAdapter.h  
  
## 請參閱  
 [階層架構圖表](../../mfc/hierarchy-chart.md)   
 [類別](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)