---
title: is_trivially_default_constructible Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 7378e982af31c1030012934924a053666fb4fff2
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible Class
Tests if type has trivial default constructor.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct is_trivially_default_constructible;
```  
  
#### <a name="parameters"></a>Parameters  
 `Ty`  
 The type to query.  
  
## <a name="remarks"></a>Remarks  
 An instance of the type predicate holds true if the type `Ty` is a class that has a trivial constructor, otherwise it holds false.  
  
 A default constructor for a class `Ty` is trivial if:  
  
-   it is an implicitly declared default constructor  
  
-   the class `Ty` has no virtual functions  
  
-   the class `Ty` has no virtual bases  
  
-   all the direct bases of the class `Ty` have trivial constructors  
  
-   the classes of all the non-static data members of class type have trivial constructors  
  
-   the classes of all the non-static data members of type array of class have trivial constructors  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [<type_traits>](../standard-library/type-traits.md)




