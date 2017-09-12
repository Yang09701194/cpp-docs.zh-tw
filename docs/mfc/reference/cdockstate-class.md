---
title: CDockState Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
dev_langs:
- C++
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: 23
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
ms.openlocfilehash: 8b16523382c1530f0c7c1022e632be0339801cfb
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cdockstate-class"></a>CDockState Class
A serialized `CObject` class that loads, unloads, or clears the state of one or more docking control bars in persistent memory (a file).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDockState : public CObject  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CDockState::Clear](#clear)|Clears the dock state information.|  
|[CDockState::GetVersion](#getversion)|Retrieves the version number of the stored bar state.|  
|[CDockState::LoadState](#loadstate)|Retrieves state information from the registry or .INI file.|  
|[CDockState::SaveState](#savestate)|Saves state information to the registry or INI file.|  
  
### <a name="public-data-members"></a>Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|Array of pointers to the stored dock state information with one entry for each control bar.|  
  
## <a name="remarks"></a>Remarks  
 The dock state includes the size and position of the bar and whether or not it is docked. When retrieving the stored dock state, `CDockState` checks the bar's position and, if the bar is not visible with the current screen settings, `CDockState` scales the bar's position so that it is visible. The main purpose of `CDockState` is to hold the entire state of a number of control bars and to allow that state to be saved and loaded either to the registry, the application's .INI file, or in binary form as part of a `CArchive` object's contents.  
  
 The bar can be any dockable control bar, including a toolbar, status bar, or dialog bar. `CDockState` objects are written and read to or from a file via a `CArchive` object.  
  
 [CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) retrieves the state information of all the frame window's `CControlBar` objects and puts it into the `CDockState` object. You can then write the contents of the `CDockState` object to storage with [Serialize](../../mfc/reference/cobject-class.md#serialize) or [CDockState::SaveState](#savestate). If you later want to restore the state of the control bars in the frame window, you can load the state with `Serialize` or [CDockState::LoadState](#loadstate), then use [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) to apply the saved state to the frame window's control bars.  
  
 For more information on docking control bars, see the articles [Control Bars](../../mfc/control-bars.md), [Toolbars: Docking and Floating](../../mfc/docking-and-floating-toolbars.md), and [Frame Windows](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxadv.h  
  
##  <a name="clear"></a>  CDockState::Clear  
 Call this function to clear all docking information stored in the `CDockState` object.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarks  
 This includes not only whether the bar is docked or not, but the bar's size and position and whether or not it is visible.  
  
##  <a name="getversion"></a>  CDockState::GetVersion  
 Call this function to retrieve the version number of the stored bar state.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Return Value  
 1 if the stored bar information is older than current bar state; 2 if the stored bar information is the same as the current bar state.  
  
### <a name="remarks"></a>Remarks  
 Version support enables a revised bar to add new persistent properties and still be able to detect and load the persistent state created by an earlier version of the bar.  
  
##  <a name="loadstate"></a>  CDockState::LoadState  
 Call this function to retrieve state information from the registry or .INI file.  
  
```  
void LoadState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parameters  
 `lpszProfileName`  
 Points to a null-teminated string that specifies the name of a section in the initialization file or a key in the Windows registry where state information is stored.  
  
### <a name="remarks"></a>Remarks  
 The profile name is the section of the application's .INI file or the registry that contains the bars' state information. You can save control bar state information to the registry or .INI file with `SaveState`.  
  
##  <a name="m_arrbarinfo"></a>  CDockState::m_arrBarInfo  
 A `CPtrArray` object that is an array of pointers to the stored control bar information for each control bar that has saved state information in the `CDockState` object.  
  
```  
CPtrArray m_arrBarInfo;  
```  
  
##  <a name="savestate"></a>  CDockState::SaveState  
 Call this function to save the state information to the registry or .INI file.  
  
```  
void SaveState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parameters  
 `lpszProfileName`  
 Points to a null-teminated string that specifies the name of a section in the initialization file or a key in the Windows registry where state information is stored.  
  
### <a name="remarks"></a>Remarks  
 The profile name is the section of the application's .INI file or the registry that contains the control bar's state information. `SaveState` also saves the current screen size. You can retrieve control bar information from the registry or .INI file with `LoadState`.  
  
## <a name="see-also"></a>See Also  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)


