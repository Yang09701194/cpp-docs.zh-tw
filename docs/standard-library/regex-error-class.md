---
title: regex_error Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
dev_langs:
- C++
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
caps.latest.revision: 19
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
ms.openlocfilehash: b62638529f90240201ae229b6ae647e8a87fdf95
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="regexerror-class"></a>regex_error Class
Reports a bad basic_regex object.  
  
## <a name="syntax"></a>Syntax  
  
```  
class regex_error  
 : public std::runtime_error {  
public:  
    explicit regex_error(regex_constants::error_code error);

    regex_constants::error_code code() const;

 
 };  
```  
  
## <a name="remarks"></a>Remarks  
 The class describes an exception object thrown to report an error in the construction or use of a `basic_regex` object.  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<regex>  
  
 **Namespace:** std  
  
##  <a name="code"></a>  regex_error::code  
 Returns the error code.  
  
```  
regex_constants::error_code code() const;
```  
  
### <a name="remarks"></a>Remarks  
 The member function returns the value that was passed to the object's constructor.  
  
### <a name="example"></a>Example  
  
```cpp  
// std__regex__regex_error_code.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex_error paren(std::regex_constants::error_paren);   
  
    try   
        {   
        std::regex rx("(a");   
        }   
    catch (const std::regex_error& rerr)   
        {   
        std::cout << "regex error: "   
            << (rerr.code() == paren.code()   
                 "unbalanced parentheses" : "")   
            << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
```Output  
regex error: unbalanced parentheses  
```  
  
##  <a name="regex_error"></a>  regex_error::regex_error  
 Constructs the object.  
  
```  
regex_error(regex_constants::error_code error);
```  
  
### <a name="parameters"></a>Parameters  
 `error`  
 The error code.  
  
### <a name="remarks"></a>Remarks  
 The constructor constructs an object that holds the value `error`.  
  
### <a name="example"></a>Example  
  
```cpp  
// std__regex__regex_error_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex_error paren(std::regex_constants::error_paren);   
  
    try   
        {   
        std::regex rx("(a");   
        }   
    catch (const std::regex_error& rerr)   
        {   
        std::cout << "regex error: "   
            << (rerr.code() == paren.code()   
                 "unbalanced parentheses" : "")   
            << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
```Output  
regex error: unbalanced parentheses  
```  
  
## <a name="see-also"></a>See Also  
[\<regex>](../standard-library/regex.md)  
[regex_constants Class](../standard-library/regex-constants-class.md)  
[\<regex> functions](../standard-library/regex-functions.md)  
[regex_iterator Class](../standard-library/regex-iterator-class.md)  
[\<regex> operators](../standard-library/regex-operators.md)  
[regex_token_iterator Class](../standard-library/regex-token-iterator-class.md)  
[regex_traits Class](../standard-library/regex-traits-class.md)  
[\<regex> typedefs](../standard-library/regex-typedefs.md)  

