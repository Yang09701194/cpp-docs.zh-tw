---
title: CShellManager Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CShellManager
- AFXSHELLMANAGER/CShellManager
- AFXSHELLMANAGER/CShellManager::CShellManager
- AFXSHELLMANAGER/CShellManager::BrowseForFolder
- AFXSHELLMANAGER/CShellManager::ConcatenateItem
- AFXSHELLMANAGER/CShellManager::CopyItem
- AFXSHELLMANAGER/CShellManager::CreateItem
- AFXSHELLMANAGER/CShellManager::FreeItem
- AFXSHELLMANAGER/CShellManager::GetItemCount
- AFXSHELLMANAGER/CShellManager::GetItemSize
- AFXSHELLMANAGER/CShellManager::GetNextItem
- AFXSHELLMANAGER/CShellManager::GetParentItem
- AFXSHELLMANAGER/CShellManager::ItemFromPath
dev_langs:
- C++
helpviewer_keywords:
- CShellManager [MFC], CShellManager
- CShellManager [MFC], BrowseForFolder
- CShellManager [MFC], ConcatenateItem
- CShellManager [MFC], CopyItem
- CShellManager [MFC], CreateItem
- CShellManager [MFC], FreeItem
- CShellManager [MFC], GetItemCount
- CShellManager [MFC], GetItemSize
- CShellManager [MFC], GetNextItem
- CShellManager [MFC], GetParentItem
- CShellManager [MFC], ItemFromPath
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
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
ms.openlocfilehash: b8ea86dd42a701d441c53effe51db9081ea0b48d
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cshellmanager-class"></a>CShellManager Class
Implements several methods that enable you to work with pointers to identifier lists (PIDLs).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CShellManager : public CObject  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CShellManager::CShellManager](#cshellmanager)|Constructs a `CShellManager` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CShellManager::BrowseForFolder](#browseforfolder)|Displays a dialog box that enables the user to select a shell folder.|  
|[CShellManager::ConcatenateItem](#concatenateitem)|Concatenates two PIDLs.|  
|[CShellManager::CopyItem](#copyitem)|Creates a new PIDL and copies the supplied PIDL to it.|  
|[CShellManager::CreateItem](#createitem)|Creates a new PIDL of the specified size.|  
|[CShellManager::FreeItem](#freeitem)|Deletes the supplied PIDL.|  
|[CShellManager::GetItemCount](#getitemcount)|Returns the number of items in the supplied PIDL.|  
|[CShellManager::GetItemSize](#getitemsize)|Returns the size of the supplied PIDL.|  
|[CShellManager::GetNextItem](#getnextitem)|Returns the next item from the PIDL.|  
|[CShellManager::GetParentItem](#getparentitem)|Retrieves the parent item of the supplied item.|  
|[CShellManager::ItemFromPath](#itemfrompath)|Retrieves the PIDL for the item identified by the supplied path.|  
  
## <a name="remarks"></a>Remarks  
 The methods of the `CShellManager` class all deal with PIDLs. A PIDL is a unique identifier for a shell object.  
  
 You should not create a `CShellManager` object manually. It will be created automatically by the framework of your application. However, you should call [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) during the initialization process of your application. To get a pointer to the shell manager for your application, call [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxshellmanager.h  
  
##  <a name="browseforfolder"></a>  CShellManager::BrowseForFolder  
 Displays a dialog box that enables the user to select a shell folder.  
  
```  
BOOL BrowseForFolder(
    CString& strOutFolder,  
    CWnd* pWndParent = NULL,  
    LPCTSTR lplszInitialFolder = NULL,  
    LPCTSTR lpszTitle = NULL,  
    UINT ulFlags = BIF_RETURNONLYFSDIRS,  
    LPINT piFolderImage = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 [out] `strOutFolder`  
 The string used by the method to store the path of the selected folder.  
  
 [in] `pWndParent`  
 A pointer to the parent window.  
  
 [in] `lplszInitialFolder`  
 A string that contains the folder that is selected by default when the dialog box is displayed.  
  
 [in] `lpszTitle`  
 The title for the dialog box.  
  
 [in] `ulFlags`  
 Flags specifying options for the dialog box. See [BROWSEINFO](http://msdn.microsoft.com/library/windows/desktop/bb773205) for the detailed description.  
  
 [out] `piFolderImage`  
 A pointer to the integer value where the method writes the image index of the selected folder.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the user selects a folder from the dialog box; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 When you call this method, the application creates and shows a dialog box that enables the user to select a folder. The method will write the path of the folder into the `strOutFolder` parameter.  
  
### <a name="example"></a>Example  
 The following example demonstrates how to retrieve a reference to a `CShellManager` object by using the `CWinAppEx::GetShellManager` method and how to use the `BrowseForFolder` method. This code snippet is part of the [Explorer sample](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]  
  
##  <a name="concatenateitem"></a>  CShellManager::ConcatenateItem  
 Creates a new list containing two PIDLs.  
  
```  
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,  
    LPCITEMIDLIST pidl2);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pidl1`  
 The first item.  
  
 [in] `pidl2`  
 The second item.  
  
### <a name="return-value"></a>Return Value  
 A pointer to the new item list if the function succeeds, otherwise `NULL`.  
  
### <a name="remarks"></a>Remarks  
 This method creates a new [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) large enough to contain both `pidl1` and `pidl2`. It then copies `pidl1` and `pidl2` to the new list.  
  
##  <a name="copyitem"></a>  CShellManager::CopyItem  
 Copies an item list.  
  
```  
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pidlSource`  
 The original item list.  
  
### <a name="return-value"></a>Return Value  
 A pointer to the newly created item list if successful; otherwise `NULL`.  
  
### <a name="remarks"></a>Remarks  
 The newly created item list has the same size as the source item list.  
  
##  <a name="createitem"></a>  CShellManager::CreateItem  
 Creates a new PIDL.  
  
```  
LPITEMIDLIST CreateItem(UINT cbSize);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `cbSize`  
 The size of the item list.  
  
### <a name="return-value"></a>Return Value  
 A pointer to the created item list if successful; otherwise `NULL`.  
  
##  <a name="cshellmanager"></a>  CShellManager::CShellManager  
 Constructs a `CShellManager` object.  
  
```  
CShellManager();
```  
  
### <a name="remarks"></a>Remarks  
 In most cases, you do not have to create a `CShellManager` directly. By default, the framework creates one for you. To get a pointer to the `CShellManager`, call [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager). If you do create a `CShellManager` manually, you must initialize it with the method [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager).  
  
##  <a name="freeitem"></a>  CShellManager::FreeItem  
 Deletes an item list.  
  
```  
void FreeItem(LPITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pidl`  
 An item list to delete.  
  
##  <a name="getitemcount"></a>  CShellManager::GetItemCount  
 Returns the number of items in an item list.  
  
```  
UINT GetItemCount(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pidl`  
 A pointer to an item list.  
  
### <a name="return-value"></a>Return Value  
 The number of items in the item list.  
  
##  <a name="getitemsize"></a>  CShellManager::GetItemSize  
 Returns the size of an item list.  
  
```  
UINT GetItemSize(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pidl`  
 A pointer to an item list.  
  
### <a name="return-value"></a>Return Value  
 The size of the item list.  
  
##  <a name="getnextitem"></a>  CShellManager::GetNextItem  
 Retrieves the next item from a pointer to an item identifier list (PIDL).  
  
```  
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pidl`  
 The list of items to iterate.  
  
### <a name="return-value"></a>Return Value  
 A pointer to the next item in the list.  
  
### <a name="remarks"></a>Remarks  
 If there are no more items in the list, this method returns `NULL`.  
  
##  <a name="getparentitem"></a>  CShellManager::GetParentItem  
 Retrieves the parent of a pointer to an item identifier list (PIDL).  
  
```  
int GetParentItem(
    LPCITEMIDLIST lpidl,  
    LPITEMIDLIST& lpidlParent);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `lpidl`  
 A PIDL whose parent will be retrieved.  
  
 [out] `lpidlParent`  
 A reference to a PIDL where the method will store the result.  
  
### <a name="return-value"></a>Return Value  
 The level of the parent PIDL.  
  
### <a name="remarks"></a>Remarks  
 The level of a PIDL is relative to the desktop. The desktop PIDL is considered to have a level of 0.  
  
##  <a name="itemfrompath"></a>  CShellManager::ItemFromPath  
 Retrieves the pointer to an item identifier list (PIDL) from the item identified by a string path.  
  
```  
HRESULT ItemFromPath(
    LPCTSTR lpszPath,  
    LPITEMIDLIST& pidl);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `lpszPath`  
 A string that specifies the path for the item.  
  
 [out] `pidl`  
 A reference to a PIDL. The method uses this PIDL to store the pointer to its return value.  
  
### <a name="return-value"></a>Return Value  
 Returns `NOERROR` if successful; an OLE-defined error value.  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

