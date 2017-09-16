---
title: '&lt;strstream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<strstream>", "<strstream>
dev_langs:
- C++
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
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
ms.openlocfilehash: dfd5120f518a1de5bc035537d99dfa725686be1b
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;
Defines several classes that support iostreams operations on sequences stored in an allocated array of `char` object. Such sequences are easily converted to and from C strings.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <strstream>  
  
```  
  
## <a name="remarks"></a>Remarks  
 Objects of type `strstream` work with `char` *, which are C strings. Use [\<sstream>](../standard-library/sstream.md) to work with objects of type [basic_string](../standard-library/basic-string-class.md).  
  
> [!NOTE]
>  The classes in `<strstream>` are deprecated. Consider using the classes in `<sstream>` instead.  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[strstreambuf Class](../standard-library/strstreambuf-class.md)|The class describes a stream buffer that controls the transmission of elements to and from a sequence of elements stored in a `char` array object.|  
|[istrstream Class](../standard-library/istrstream-class.md)|The class describes an object that controls extraction of elements and encoded objects from a stream buffer of class [strstreambuf](../standard-library/strstreambuf-class.md).|  
|[ostrstream Class](../standard-library/ostrstream-class.md)|The class describes an object that controls insertion of elements and encoded objects into a stream buffer of class [strstreambuf](../standard-library/strstreambuf-class.md).|  
|[strstream Class](../standard-library/strstream-class.md)|The class describes an object that controls insertion and extraction of elements and encoded objects using a stream buffer of class [strstreambuf](../standard-library/strstreambuf-class.md).|  
  
## <a name="see-also"></a>See Also  
 [\<strstream>](../standard-library/strstream.md)   
 [Header Files Reference](../standard-library/cpp-standard-library-header-files.md)   
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream Programming](../standard-library/iostream-programming.md)   
 [iostreams Conventions](../standard-library/iostreams-conventions.md)




