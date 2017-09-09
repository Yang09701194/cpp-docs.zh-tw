---
title: hash Structure (C++ Standard Library)| Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::hash
dev_langs:
- C++
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
caps.latest.revision: 13
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 3a5e3c107bc5105e7de92bcb6b42c7de20baf475
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="hash-structure-c-standard-library"></a>hash Structure (C++ Standard Library)
Defines a member function that returns a value that's uniquely determined by `Val`. The member function defines a [hash](../standard-library/hash-class.md) function that's suitable for mapping values of type `thread::id` to a distribution of index values.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <>  
struct hash<thread::id> :   
    public unary_function<thread::id, size_t>  
{  
    size_t operator()(thread::id Val) const;

 
};  
```  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<thread>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [Header Files Reference](../standard-library/cpp-standard-library-header-files.md)   
 [\<thread>](../standard-library/thread.md)   
 [unary_function Struct](../standard-library/unary-function-struct.md)

