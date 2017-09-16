---
title: out_of_range Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdexcept/std::out_of_range
dev_langs:
- C++
helpviewer_keywords:
- out_of_range class
ms.assetid: d0e14dc0-065e-4666-9ac9-51e52223c503
caps.latest.revision: 25
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
ms.openlocfilehash: cfdc765f6246574ee09118e70654aac2ec81e205
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="outofrange-class"></a>out_of_range Class
The class serves as the base class for all exceptions thrown to report an argument that is out of its valid range.  
  
## <a name="syntax"></a>Syntax  
  
```  
class out_of_range : public logic_error {  
public:  
    explicit out_of_range(const string& message);

    explicit out_of_range(const char *message);

};  
```  
  
## <a name="remarks"></a>Remarks  
 The value returned by [what](../standard-library/exception-class.md) is a copy of **message**`.`[data](../standard-library/basic-string-class.md#data).  
  
## <a name="example"></a>Example  
  
```cpp  
// out_of_range.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
using namespace std;  
  
int main() {  
// out_of_range  
   try {  
      string str( "Micro" );  
      string rstr( "soft" );  
      str.append( rstr, 5, 3 );  
      cout << str << endl;  
   }  
   catch ( exception &e ) {  
      cerr << "Caught: " << e.what( ) << endl;  
   };  
}  
```  
  
## <a name="output"></a>Output  
  
```  
Caught: invalid string position  
```  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<stdexcept>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [logic_error Class](../standard-library/logic-error-class.md)   
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)


