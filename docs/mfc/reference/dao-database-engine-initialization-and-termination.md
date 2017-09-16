---
title: DAO Database Engine Initialization and Termination | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
caps.latest.revision: 13
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
ms.openlocfilehash: 46bacd608c5cf37b148c7ea4b9096fa63681d1d3
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO Database Engine Initialization and Termination
When using MFC DAO objects, the DAO database engine must first be initialized and then terminated before your application or DLL quits. Two functions, `AfxDaoInit` and `AfxDaoTerm`, perform these tasks.  
  
### <a name="dao-database-engine-initialization-and-termination"></a>DAO Database Engine Initialization and Termination  
  
|||  
|-|-|  
|[AfxDaoInit](#afxdaoinit)|Initializes the DAO database engine.|  
|[AfxDaoTerm](#afxdaoterm)|Terminates the DAO database engine.|  
  
##  <a name="afxdaoinit"></a>  AfxDaoInit  
 This function initializes the DAO database engine.  
  
```  
 
void AfxDaoInit();

throw(CDaoException*);  
```  
  
### <a name="remarks"></a>Remarks  
 In most cases, you don't need to call `AfxDaoInit` because the application automatically calls it when it is needed.  
  
 For related information, and for an example of calling `AfxDaoInit`, see [Technical Note 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
### <a name="requirements"></a>Requirements  
  **Header** afxdao.h  
  
##  <a name="afxdaoterm"></a>  AfxDaoTerm  
 This function terminates the DAO database engine.  
  
```  
 
void AfxDaoTerm();  
```  
  
### <a name="remarks"></a>Remarks  
 Typically, you only need to call this function in a regular MFC DLL; an application will automatically call `AfxDaoTerm` when it is needed.  
  
 In regular MFC DLLs, call `AfxDaoTerm` before the `ExitInstance` function, but after all MFC DAO objects have been destroyed.  
  
 For related information, see [Technical Note 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  

### <a name="requirements"></a>Requirements  
  **Header** afxdao.h  

## <a name="see-also"></a>See Also  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

