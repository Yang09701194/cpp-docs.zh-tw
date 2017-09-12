---
title: CStringList Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringList
- AFXCOLL/CStringList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
caps.latest.revision: 25
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
ms.openlocfilehash: e92526991a7f7554f868a36d655766cf7f1304f4
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cstringlist-class"></a>CStringList Class
Supports lists of `CString` objects.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CStringList : public CObject  
```  
  
## <a name="members"></a>Members  
 The member functions of `CStringList` are similar to the member functions of class [CObList](../../mfc/reference/coblist-class.md). Because of this similarity, you can use the `CObList` reference documentation for member function specifics. Wherever you see a `CObject` pointer as a return value, substitute a `CString` (not a `CString` pointer). Wherever you see a `CObject` pointer as a function parameter, substitute an `LPCTSTR`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 for example, translates to  
  
 `CString& CStringList::GetHead() const;`  
  
 and  
  
 `POSITION AddHead( CObject* <newElement> );`  
  
 translates to  
  
 `POSITION AddHead( LPCTSTR <newElement> );`  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CObList::CObList](../../mfc/reference/coblist-class.md#coblist)|Constructs an empty list.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CObList::AddHead](../../mfc/reference/coblist-class.md#addhead)|Adds an element (or all the elements in another list) to the head of the list (makes a new head).|  
|[CObList::AddTail](../../mfc/reference/coblist-class.md#addtail)|Adds an element (or all the elements in another list) to the tail of the list (makes a new tail).|  
|[CObList::Find](../../mfc/reference/coblist-class.md#find)|Gets the position of an element specified by pointer value.|  
|[CObList::FindIndex](../../mfc/reference/coblist-class.md#findindex)|Gets the position of an element specified by a zero-based index.|  
|[CObList::GetAt](../../mfc/reference/coblist-class.md#getat)|Gets the element at a given position.|  
|[CObList::GetCount](../../mfc/reference/coblist-class.md#getcount)|Returns the number of elements in this list.|  
|[CObList::GetHead](../../mfc/reference/coblist-class.md#gethead)|Returns the head element of the list (cannot be empty).|  
|[CObList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|Returns the position of the head element of the list.|  
|[CObList::GetNext](../../mfc/reference/coblist-class.md#getnext)|Gets the next element for iterating.|  
|[CObList::GetPrev](../../mfc/reference/coblist-class.md#getprev)|Gets the previous element for iterating.|  
|[CObList::GetSize](../../mfc/reference/coblist-class.md#getsize)|Returns the number of elements in this list.|  
|[CObList::GetTail](../../mfc/reference/coblist-class.md#gettail)|Returns the tail element of the list (cannot be empty).|  
|[CObList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|Returns the position of the tail element of the list.|  
|[CObList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|Inserts a new element after a given position.|  
|[CObList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|Inserts a new element before a given position.|  
|[CObList::IsEmpty](../../mfc/reference/coblist-class.md#isempty)|Tests for the empty list condition (no elements).|  
|[CObList::RemoveAll](../../mfc/reference/coblist-class.md#removeall)|Removes all the elements from this list.|  
|[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|Removes an element from this list, specified by position.|  
|[CObList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|Removes the element from the head of the list.|  
|[CObList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|Removes the element from the tail of the list.|  
|[CObList::SetAt](../../mfc/reference/coblist-class.md#setat)|Sets the element at a given position.|  
  
## <a name="remarks"></a>Remarks  
 All comparisons are done by value, meaning that the characters in the string are compared instead of the addresses of the strings.  
  
 `CStringList` incorporates the `IMPLEMENT_SERIAL` macro to support serialization and dumping of its elements. If a list of `CString` objects is stored to an archive, either with an overloaded insertion operator or with the `Serialize` member function, each `CString` element is serialized in turn.  
  
 If you need a dump of individual `CString` elements, you must set the depth of the dump context to 1 or greater.  
  
 For more information on using `CStringList`, see the article [Collections](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringList`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxcoll.h  
  
## <a name="see-also"></a>See Also  
 [MFC Sample COLLECT](../../visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)




