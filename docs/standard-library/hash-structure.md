---
title: hash Structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- typeindex/std::hash
dev_langs:
- C++
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
caps.latest.revision: 13
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
ms.openlocfilehash: 3babf77f4dda4c3bd7341b00d79153b7297820da
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="hash-structure"></a>hash Structure
The template class defines its method as returning `val.hash_code()`. The method defines a hash function that is used to map values of type [type_index](../standard-library/type-index-class.md) to a distribution of index values.  
  
## <a name="syntax"></a>Syntax  
  
```
template <>
struct hash<type_index>  
: public unary_function<type_index, size_t>
 { // hashes a typeinfo object
    size_t operator()(type_index val) const;

 };
```  
  
## <a name="see-also"></a>See Also  
 [\<typeindex>](../standard-library/typeindex.md)




