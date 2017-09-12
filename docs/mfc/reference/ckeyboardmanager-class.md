---
title: CKeyboardManager Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
dev_langs:
- C++
helpviewer_keywords:
- CKeyboardManager [MFC], CKeyboardManager
- CKeyboardManager [MFC], CleanUp
- CKeyboardManager [MFC], FindDefaultAccelerator
- CKeyboardManager [MFC], IsKeyHandled
- CKeyboardManager [MFC], IsKeyPrintable
- CKeyboardManager [MFC], IsShowAllAccelerators
- CKeyboardManager [MFC], LoadState
- CKeyboardManager [MFC], ResetAll
- CKeyboardManager [MFC], SaveState
- CKeyboardManager [MFC], ShowAllAccelerators
- CKeyboardManager [MFC], TranslateCharToUpper
- CKeyboardManager [MFC], UpdateAccelTable
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
caps.latest.revision: 33
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
ms.openlocfilehash: c49d5be8f9e208defeb1752c4288e212bb5dec45
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="ckeyboardmanager-class"></a>CKeyboardManager Class
Manages shortcut key tables for the main frame window and child frame windows.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CKeyboardManager : public CObject  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|||  
|-|-|  
|Name|Description|  
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Constructs a `CKeyboardManager` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|||  
|-|-|  
|Name|Description|  
|[CKeyboardManager::CleanUp](#cleanup)|Clears the shortcut key tables.|  
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Retrieves the default shortcut key for the specified command and window.|  
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Determines whether a key is handled by the accelerator table.|  
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Indicates whether a character is printable.|  
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Indicates whether menus show all shortcut keys for a command or only the default shortcut key.|  
|[CKeyboardManager::LoadState](#loadstate)|Loads the shortcut key tables from the Windows registry.|  
|[CKeyboardManager::ResetAll](#resetall)|Reloads the shortcut key tables from the application resource.|  
|[CKeyboardManager::SaveState](#savestate)|Saves the shortcut key tables to the Windows registry.|  
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Specifies whether the framework displays all the shortcut keys for all commands, or a single shortcut key for each command. This method does not affect commands that have only one associated shortcut key.|  
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Converts a character to its upper register.|  
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Updates a shortcut key table with a new shortcut key table.|  
  
## <a name="remarks"></a>Remarks  
 The members of this class enable you to save and load shortcut key tables to the Windows registry, use a template to update the short cut key tables, and find the default shortcut key for a command in a frame window. In addition, the `CKeyboardManager` object lets you control how shortcut keys are displayed to the user.  
  
 You should not create a `CKeyboardManager` object manually. It will be created automatically by the framework of your application. However, you should call [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) during the initialization process of your application. To get a pointer to the keyboard manager for your application, call [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).  
  
## <a name="example"></a>Example  
 The following example demonstrates how to retrieve a pointer to a `CKeyboardManager` object from a `CWinAppEx` class, and how to show all the shortcut keys associated with menu commands. This code snippet is part of the [Custom Pages sample](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxkeyboardmanager.h  
  
##  <a name="ckeyboardmanager"></a>  CKeyboardManager::CKeyboardManager  
 Constructs a `CKeyboardManager` object.  
  
```  
CKeyboardManager();
```  
  
### <a name="remarks"></a>Remarks  
 In most cases, you do not have to create a `CKeyboardManager` directly. By default, the framework creates one for you. To get a pointer to the `CKeyboardManager`, call [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). If you do create one manually, you must initialize it with the method [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).  
  
##  <a name="cleanup"></a>  CKeyboardManager::CleanUp  
 Frees the `CKeyboardManager` resources and clears all shortcut key mappings.  
  
```  
static void CleanUp();
```  
  
### <a name="remarks"></a>Remarks  
 For more information about shortcut keys, see [Keyboard and Mouse Customization](../../mfc/keyboard-and-mouse-customization.md).  
  
 You do not have to call this function when your application exits because the framework calls it automatically during application exit.  
  
##  <a name="finddefaultaccelerator"></a>  CKeyboardManager::FindDefaultAccelerator  
 Retrieves the default shortcut key for the specified command and window.  
  
```  
static BOOL FindDefaultAccelerator(
    UINT uiCmd,  
    CString& str,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `uiCmd`  
 The command ID.  
  
 [out] `str`  
 A reference to a `CString` object.  
  
 [in] `pWndFrame`  
 A pointer to a frame window.  
  
 [in] `bIsDefaultFrame`  
 Specifies whether the frame window is the default frame window.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the shortcut is found; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 This method looks up the command specified by `uiCmd` and retrieves the default shortcut key. Then the method takes the string associated with this shortcut key and writes the value to the `str` parameter.  
  
##  <a name="iskeyhandled"></a>  CKeyboardManager::IsKeyHandled  
 Determines whether the specified key is handled by the [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md).  
  
```  
static BOOL __stdcall IsKeyHandled(
    WORD nKey,  
    BYTE fVirt,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>Parameters  
  
|||  
|-|-|  
|Parameter|Description|  
|[in] `nKey`|The key to check.|  
|[in] `fVirt`|Specifies the behavior of the shortcut key. For a list of possible values, see [ACCEL Structure](http://msdn.microsoft.com/library/windows/desktop/ms646340).|  
|[in] `pWndFrame`|A frame window. This method determines whether a shortcut key is handled in this frame.|  
|[in] `bIsDefaultFrame`|A Boolean parameter that indicates whether `pWndFrame` is the default frame window.|  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the shortcut key is handled. `FALSE` if the key is not handled or if `pWndFrame` is `NULL`.  
  
### <a name="remarks"></a>Remarks  
 The input parameters must match the entry in the accelerator table both for `nKey` and `fVirt` to determine whether a shortcut key is handled in `pWndFrame`.  
  
##  <a name="iskeyprintable"></a>  CKeyboardManager::IsKeyPrintable  
 Indicates whether a character is printable.  
  
```  
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```  
  
### <a name="parameters"></a>Parameters  
  
|||  
|-|-|  
|Parameter|Description|  
|[in] `nChar`|The character that this method checks.|  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the character is printable, zero if it is not.  
  
### <a name="remarks"></a>Remarks  
 This method fails if a call to [GetKeyboardState](http://msdn.microsoft.com/library/windows/desktop/ms646299) fails.  
  
##  <a name="isshowallaccelerators"></a>  CKeyboardManager::IsShowAllAccelerators  
 Indicates whether menus show all the shortcut keys associated with menu commands or only the default shortcut keys.  
  
```  
static BOOL IsShowAllAccelerators();
```  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the application lists all the shortcut keys for menu commands; 0 if the application displays only default shortcut keys.  
  
### <a name="remarks"></a>Remarks  
 The application lists the shortcut keys for menu commands in the menu bar. Use the function [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) to control whether the application lists all the shortcut keys or just the default shortcut keys.  
  
##  <a name="loadstate"></a>  CKeyboardManager::LoadState  
 Loads the shortcut key tables from the Windows registry.  
  
```  
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `lpszProfileName`  
 The registry path where `CKeyboardManager` data is saved.  
  
 [in] `pDefaultFrame`  
 A pointer to a frame window to use as the default window.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the state was loaded successfully or 0 otherwise.  
  
### <a name="remarks"></a>Remarks  
 If the `lpszProfileName` parameter is `NULL`, this method checks the default registry location for `CKeyboardManager` data. The default registry location is specified by the [CWinAppEx Class](../../mfc/reference/cwinappex-class.md). The data must be previously written with the method [CKeyboardManager::SaveState](#savestate).  
  
 If you do not specify a default window, the main frame window of your application will be used.  
  
##  <a name="resetall"></a>  CKeyboardManager::ResetAll  
 Reloads the shortcut key tables from the application resource.  
  
```  
void ResetAll();
```  
  
### <a name="remarks"></a>Remarks  
 This function clears the shortcuts stored in the `CKeyboardManager` instance. It will then reload the state of the keyboard manager from the application resource.  
  
##  <a name="savestate"></a>  CKeyboardManager::SaveState  
 Saves the shortcut key tables to the Windows registry.  
  
```  
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `lpszProfileName`  
 The registry path for saving the `CKeyboardManager` state.  
  
 [in] `pDefaultFrame`  
 A pointer to a frame window that becomes the default window.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the keyboard manager state was saved successfully, or 0 otherwise.  
  
### <a name="remarks"></a>Remarks  
 If the `lpszProfileName` parameter is `NULL`, this method will write the `CKeyboardManager` state to the default location specified by the [CWinAppEx Class](../../mfc/reference/cwinappex-class.md). If you specify a location, you can load the data later using the method [CKeyboardManager::LoadState](#loadstate).  
  
 If you do not specify a default window, the main frame window will be used as the default window.  
  
##  <a name="showallaccelerators"></a>  CKeyboardManager::ShowAllAccelerators  
 Shows all the shortcut keys associated with menu commands.  
  
```  
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,  
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `bShowAll`  
 If `true`, all the shortcut keys will be displayed. If `false`, only the first shortcut key will be displayed.  
  
 [in] `lpszDelimiter`  
 A string to insert between shortcut keys. This delimiter has no effect if only one shortcut key is displayed.  
  
### <a name="remarks"></a>Remarks  
 By default, if a command has more than one shortcut key associated with it, only the first shortcut key will be shown. This function enables you to list all the shortcut keys associated with all commands.  
  
 The shortcut keys will be listed next to the command in the menu bar. If all the shortcut keys are displayed, the string provided by `lpszDelimiter` will separate individual shortcut keys.  
  
##  <a name="translatechartoupper"></a>  CKeyboardManager::TranslateCharToUpper  
 Converts a character to its upper register.  
  
```  
static UINT TranslateCharToUpper(const UINT nChar);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `nChar`  
 The character to convert.  
  
### <a name="return-value"></a>Return Value  
 The character that is the upper register of the input parameter.  
  
##  <a name="updateacceltable"></a>  CKeyboardManager::UpdateAccelTable  
 Updates a shortcut key table with a new shortcut key table.  
  
```  
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    LPACCEL lpAccel,  
    int nSize,  
    CFrameWnd* pDefaultFrame = NULL);

 
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    HACCEL hAccelNew,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pTemplate`  
 A pointer to a document template.  
  
 [in] `lpAccel`  
 A pointer to the new shortcut key.  
  
 [in] `nSize`  
 The size of the new shortcut table.  
  
 [in] `pDefaultFrame`  
 A pointer to the default frame window.  
  
 [in] `hAccelNew`  
 A handle to the new shortcut table.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the method is successful; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 Use this function to replace the existing shortcut table with new shortcut keys for several frame window objects. The function receives a document template as a parameter to obtain access to all frame window objects connected to the given document template.  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)   
 [Keyboard and Mouse Customization](../../mfc/keyboard-and-mouse-customization.md)




