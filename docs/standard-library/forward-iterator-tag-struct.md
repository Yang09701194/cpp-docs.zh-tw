---
title: forward_iterator_tag Struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xutility/std::forward_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: 20
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
ms.openlocfilehash: a6c63426b1516a99b05f31b3cd07e7c3c014bf29
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag Struct
A class that provides a return type for **iterator_category** function that represents a forward iterator.  
  
## <a name="syntax"></a>Syntax  
  
```
struct forward_iterator_tag    : public input_iterator_tag {};
```  
  
## <a name="remarks"></a>Remarks  
 The category tag classes are used as compile tags for algorithm selection. The template function needs to find out what is the most specific category of its iterator argument so that it can use the most efficient algorithm at compile time. For every iterator of type `Iterator`, `iterator_traits`< `Iterator`> **::iterator_category** must be defined to be the most specific category tag that describes the iterator's behavior.  
  
 The type is the same as **iterator**\< **Iter**> **::iterator_category** when **Iter** describes an object that can serve as a forward iterator.  
  
## <a name="example"></a>Example  
 See [iterator_traits](../standard-library/iterator-traits-struct.md) or [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) for an example of how to use the **iterator_tag**s.  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<iterator>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [input_iterator_tag Struct](../standard-library/input-iterator-tag-struct.md)   
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standard Library Reference](../standard-library/cpp-standard-library-reference.md)




