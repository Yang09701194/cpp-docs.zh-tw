---
title: CTypedPtrMap Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
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
ms.openlocfilehash: 519ab5ff8a1e959d58862f8f6f49a275cb86058d
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap Class
Provides a type-safe "wrapper" for objects of the pointer-map classes `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, and `CMapStringToPtr`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class BASE_CLASS, class KEY, class VALUE>  
class CTypedPtrMap : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Parameters  
 `BASE_CLASS`  
 Base class of the typed pointer map class; must be a pointer map class ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, or `CMapStringToPtr`).  
  
 `KEY`  
 Class of the object used as the key to the map.  
  
 `VALUE`  
 Class of the object stored in the map.  
  
## <a name="members"></a>Members  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Gets the next element for iterating.|  
|[CTypedPtrMap::Lookup](#lookup)|Returns a `KEY` based on a `VALUE`.|  
|[CTypedPtrMap::RemoveKey](#removekey)|Removes an element specified by a key.|  
|[CTypedPtrMap::SetAt](#setat)|Inserts an element into the map; replaces an existing element if a matching key is found.|  
  
### <a name="public-operators"></a>Public Operators  
  
|Name|Description|  
|----------|-----------------|  
|[CTypedPtrMap::operator [ ]](#operator_at)|Inserts an element into the map.|  
  
## <a name="remarks"></a>Remarks  
 When you use `CTypedPtrMap`, the C++ type-checking facility helps eliminate errors caused by mismatched pointer types.  
  
 Because all `CTypedPtrMap` functions are inline, use of this template does not significantly affect the size or speed of your code.  
  
 For more information on using `CTypedPtrMap`, see the articles [Collections](../../mfc/collections.md) and [Template-Based Classes](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxtempl.h  
  
##  <a name="getnextassoc"></a>  CTypedPtrMap::GetNextAssoc  
 Retrieves the map element at `rNextPosition`, then updates `rNextPosition` to refer to the next element in the map.  
  
```  
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `rPosition`  
 Specifies a reference to a **POSITION** value returned by a previous `GetNextAssoc` or `BASE_CLASS`**::GetStartPosition** call.  
  
 *KEY*  
 Template parameter specifying the type of the map's keys.  
  
 `rKey`  
 Specifies the returned key of the retrieved element.  
  
 *VALUE*  
 Template parameter specifying the type of the map's values.  
  
 `rValue`  
 Specifies the returned value of the retrieved element.  
  
### <a name="remarks"></a>Remarks  
 This function is most useful for iterating through all the elements in the map. Note that the position sequence is not necessarily the same as the key value sequence.  
  
 If the retrieved element is the last in the map, then the new value of `rNextPosition` is set to **NULL**.  
  
 This inline function calls `BASE_CLASS`**::GetNextAssoc**.  
  
##  <a name="lookup"></a>  CTypedPtrMap::Lookup  
 `Lookup` uses a hashing algorithm to quickly find the map element with a key that matches exactly.  
  
```  
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `BASE_CLASS`  
 Template parameter specifying the base class of this map's class.  
  
 `key`  
 The key of the element to be looked up.  
  
 *VALUE*  
 Template parameter specifying the type of values stored in this map.  
  
 `rValue`  
 Specifies the returned value of the retrieved element.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the element was found; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 This inline function calls `BASE_CLASS`**::Lookup**.  
  
##  <a name="operator_at"></a>  CTypedPtrMap::operator [ ]  
 This operator can be used only on the left side of an assignment statement (an l-value).  
  
```  
VALUE& operator[ ](base_class ::base_arg_key key);
```  
  
### <a name="parameters"></a>Parameters  
 *VALUE*  
 Template parameter specifying the type of values stored in this map.  
  
 `BASE_CLASS`  
 Template parameter specifying the base class of this map's class.  
  
 `key`  
 The key of the element to be looked up or created in the map.  
  
### <a name="remarks"></a>Remarks  
 If there is no map element with the specified key, then a new element is created. There is no "right side" (r-value) equivalent to this operator because there is a possibility that a key may not be found in the map. Use the `Lookup` member function for element retrieval.  
  
##  <a name="removekey"></a>  CTypedPtrMap::RemoveKey  
 This member function calls `BASE_CLASS`**::RemoveKey**.  
  
```  
BOOL RemoveKey(KEY key);
```  
  
### <a name="parameters"></a>Parameters  
 *KEY*  
 Template parameter specifying the type of the map's keys.  
  
 `key`  
 Key for the element to be removed.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the entry was found and successfully removed; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 For more detailed remarks, see [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).  
  
##  <a name="setat"></a>  CTypedPtrMap::SetAt  
 This member function calls `BASE_CLASS`**::SetAt**.  
  
```  
void SetAt(KEY key, VALUE newValue);
```  
  
### <a name="parameters"></a>Parameters  
 *KEY*  
 Template parameter specifying the type of the map's keys.  
  
 `key`  
 Specifies the key value of the newValue.  
  
 `newValue`  
 Specifies the object pointer that is the value of the new element.  
  
### <a name="remarks"></a>Remarks  
 For more detailed remarks, see [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).  
  
## <a name="see-also"></a>See Also  
 [MFC Sample COLLECT](../../visual-cpp-samples.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr Class](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord Class](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr Class](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr Class](../../mfc/reference/cmapstringtoptr-class.md)

