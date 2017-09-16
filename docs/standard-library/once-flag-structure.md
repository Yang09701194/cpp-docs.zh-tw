---
title: once_flag Structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 8e7d664bf6ccde646ada9419f4577ac37dcd1ed6
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="onceflag-structure"></a>once_flag Structure
Represents a `struct` that is used with the template function [call_once](../standard-library/mutex-functions.md#call_once) to ensure that initialization code is called only once, even in the presence of multiple threads of execution.  
  
## <a name="syntax"></a>Syntax  
  
struct once_flag { constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag& operator=(const once_flag&); };  
  
## <a name="remarks"></a>Remarks  
 The `once_flag` `struct` has only a default constructor.  
  
 Objects of type `once_flag` can be created, but they cannot be copied.  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<mutex>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [Header Files Reference](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




