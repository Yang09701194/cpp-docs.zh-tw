---
title: CMFCKeyMapDialog Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::DoModal
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::FormatItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::GetCommandKeys
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnInsertItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintHeader
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnSetColumns
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::PrintKeyMap
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::SetColumnsWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCKeyMapDialog [MFC], CMFCKeyMapDialog
- CMFCKeyMapDialog [MFC], DoModal
- CMFCKeyMapDialog [MFC], FormatItem
- CMFCKeyMapDialog [MFC], GetCommandKeys
- CMFCKeyMapDialog [MFC], OnInsertItem
- CMFCKeyMapDialog [MFC], OnPrintHeader
- CMFCKeyMapDialog [MFC], OnPrintItem
- CMFCKeyMapDialog [MFC], OnSetColumns
- CMFCKeyMapDialog [MFC], PrintKeyMap
- CMFCKeyMapDialog [MFC], SetColumnsWidth
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
caps.latest.revision: 26
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
ms.openlocfilehash: 53142cc9536fdea778e9725378415e2c44be3042
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog Class
The `CMFCKeyMapDialog` class supports a control that maps commands to keys on the keyboard.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCKeyMapDialog : public CDialogEx  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|Constructs a `CMFCKeyMapDialog` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCKeyMapDialog::DoModal](#domodal)|Displays a keyboard mapping dialog box.|  
  
### <a name="protected-methods"></a>Protected Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCKeyMapDialog::FormatItem](#formatitem)|Called by the framework to build a string that describes a key mapping. By default, the string contains the command name, the shortcut keys used, and the shortcut key description.|  
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|Retrieves a string that contains a list of shortcut keys associated with the specified command.|  
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|Called by the framework before a new item is inserted into the internal list control that supports the keyboard mapping control.|  
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|Called by the framework to print the header for the keyboard map on a new page.|  
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|Called by the framework to print a keyboard mapping item.|  
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|Called by the framework to set captions for the columns in the internal list control that supports the keyboard mapping control.|  
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|Called by the framework when a user clicks the **Print** button.|  
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|Called by the framework to set the width of the columns in the internal list control that supports the keyboard mapping control.|  
  
## <a name="remarks"></a>Remarks  
 Use the `CMFCKeyMapDialog` class to implement a resizable keyboard mapping dialog box. The dialog box uses a list view control to display keyboard shortcuts and their associated commands.  
  
 To use the `CMFCKeyMapDialog` class in an application, pass in a pointer to the main frame window as a parameter to the `CMFCKeyMapDialog` constructor. Then call the `DoModal` method to start a modal dialog box.  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxkeymapdialog.h  
  
##  <a name="cmfckeymapdialog"></a>  CMFCKeyMapDialog::CMFCKeyMapDialog  
 Constructs a `CMFCKeyMapDialog` object.  
  
```  
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bEnablePrint=FALSE);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pWndParentFrame`  
 A pointer to the parent window of the `CMFCKeyMapDialog` object.  
  
 [in] `bEnablePrint`  
 `TRUE` if the list of accelerator keys can be printed; otherwise, `FALSE`. The default is `FALSE`.  
  
### <a name="remarks"></a>Remarks  
  
### <a name="example"></a>Example  
 The following example demonstrates how to construct an object of the `CMFCKeyMapDialog` class. This example is part of the [Visual Studio Demo sample](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>  CMFCKeyMapDialog::DoModal  
 Displays a keyboard mapping dialog box.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Return Value  
 A signed integer, such as `IDOK` or `IDCANCEL`, that is passed to the [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) method. The method, in turn, closes the dialog box. For more information, see [CDialog::DoModal](../../mfc/reference/cdialog-class.md#domodal).  
  
### <a name="remarks"></a>Remarks  
 The keyboard mapping dialog box enables you to select and assign accelerator keys to various categories of commands. In addition, you can copy the selected accelerator keys and their description to the clipboard.  
  
##  <a name="formatitem"></a>  CMFCKeyMapDialog::FormatItem  
 Called by the framework to build a string that describes a key mapping. By default, the string contains the command name, the shortcut keys used, and the shortcut key description.  
  
```  
virtual CString FormatItem(int nItem) const;  
```  
  
### <a name="parameters"></a>Parameters  
 [in] `nItem`  
 The zero-based index of an item in the internal list of key mappings.  
  
### <a name="return-value"></a>Return Value  
 A `CString` object that contains the formatted item text.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcommandkeys"></a>  CMFCKeyMapDialog::GetCommandKeys  
 Retrieves a string value. The string contains a list of shortcut keys that are associated with a specified command.  
  
```  
virtual CString GetCommandKeys(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>Parameters  
 [in] `uiCmdID`  
 A command ID.  
  
### <a name="return-value"></a>Return Value  
 A semicolon-delimited (';') list of shortcut keys that is associated with the specified command.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="oninsertitem"></a>  CMFCKeyMapDialog::OnInsertItem  
 Called by the framework before a new item is inserted into an internal list control that supports the keyboard mapping control.  
  
```  
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,  
    int nItem);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pButton`  
 A pointer to a toolbar button that is used to map a keyboard key combination to a command name and description. The key map item is stored in an internal list control.  
  
 [in] `nItem`  
 A zero-based index that specifies where to insert the new key map item in the internal list control.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onprintheader"></a>  CMFCKeyMapDialog::OnPrintHeader  
 Called by the framework to print the header for the keyboard map on a new page.  
  
```  
virtual int OnPrintHeader(
    CDC& dc,  
    int nPage,  
    int cx) const;  
```  
  
### <a name="parameters"></a>Parameters  
 [in] `dc`  
 The device context for the printer.  
  
 [in] `nPage`  
 The page number to print.  
  
 [in] `cx`  
 The horizontal offset of the header, in pixels.  
  
### <a name="return-value"></a>Return Value  
 If successful, the height of the printed text. For more information, see the Return Value section of [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext).  
  
### <a name="remarks"></a>Remarks  
 The framework uses this method to print the keyboard map. By default, this method prints the page number, application name, and dialog box title.  
  
##  <a name="onprintitem"></a>  CMFCKeyMapDialog::OnPrintItem  
 Called by the framework to print a keyboard mapping item.  
  
```  
virtual int OnPrintItem(
    CDC& dc,  
    int nItem,  
    int y,  
    int cx,  
    BOOL bCalcHeight) const;  
```  
  
### <a name="parameters"></a>Parameters  
 [in] `dc`  
 The device context of the printer.  
  
 [in] `nItem`  
 The zero-based index of the item to print.  
  
 [in] `y`  
 The vertical offset between the top of the page and the position of the item.  
  
 [in] `cx`  
 The horizontal offset between the left of the page and the position of the item.  
  
 [in] `bCalcHeight`  
 `TRUE` to calculate the best height for the print item; `FALSE` to truncate the print item so that it fits the default space.  
  
### <a name="return-value"></a>Return Value  
 The height of the printed item.  
  
### <a name="remarks"></a>Remarks  
 The framework calls this method to print a key map dialog box item. By default, this method prints the item's command name, shortcut keys, and command description.  
  
##  <a name="onsetcolumns"></a>  CMFCKeyMapDialog::OnSetColumns  
 Called by the framework to set captions for the columns in the internal list control that supports the keyboard mapping control.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Remarks  
 By default, this method obtains the captions for the columns from three resources. The command column caption is from IDS_AFXBARRES_COMMAND, the key column caption is from IDS_AFXBARRES_KEYS, and the description column caption is from IDS_AFXBARRES_DESCRIPTION.  
  
##  <a name="printkeymap"></a>  CMFCKeyMapDialog::PrintKeyMap  
 Called by the framework when a user clicks the **Print** button.  
  
```  
virtual void PrintKeyMap();
```  
  
### <a name="remarks"></a>Remarks  
 The `PrintKeyMap` method prints the key map. It initiates a new print job and then repeatedly calls the [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) and [CMFCKeyMapDialog::OnPrintItem](#onprintitem) methods until all the key mappings are printed.  
  
##  <a name="setcolumnswidth"></a>  CMFCKeyMapDialog::SetColumnsWidth  
 Called by the framework to set the width of the columns in the internal list control that supports the keyboard mapping control.  
  
```  
virtual void SetColumnsWidth();
```  
  
### <a name="remarks"></a>Remarks  
 This method sets the internal list control's columns to default widths. First, the width of the shortcut keys column is calculated. Then one-third of the remaining width is allocated to the command column and the remaining two-thirds is allocated to the description column.  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)

