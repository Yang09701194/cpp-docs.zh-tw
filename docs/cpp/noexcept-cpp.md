---
title: noexcept (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- noexcept_cpp
dev_langs:
- C++
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
caps.latest.revision: 5
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
ms.translationtype: HT
ms.sourcegitcommit: 39a215bb62e4452a2324db5dec40c6754d59209b
ms.openlocfilehash: 80e9ac58dcee9ee4e3028b422d0fede23f8a72f3
ms.contentlocale: zh-tw
ms.lasthandoff: 09/11/2017

---
# <a name="noexcept-c"></a>noexcept (C++)
**C++11:** Specifies whether a function might throw exceptions.  
  
## <a name="syntax"></a>Syntax  
  
> *noexcept-expression*:  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept**  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept(** *constant-expression* **)**  
  
### <a name="parameters"></a>Parameters  
 *constant-expression*  
 A constant expression of type `bool` that represents whether the set of potential exception types is empty. The unconditional version is equivalent to `noexcept(true)`.  
  
## <a name="remarks"></a>Remarks  
 A *noexcept expression* is a kind of *exception specification*, a suffix to a function declaration that represents a set of types that might be matched by an exception handler for any exception that exits a function. Unary conditional operator `noexcept(`*constant_expression*`)` where *constant_expression* yeilds `true`, and its unconditional synonym `noexcept`, specify that the set of potential exception types that can exit a function is empty. That is, the function never throws an exception and never allows an exception to be propagated outside its scope. The operator `noexcept(`*constant_expression*`)` where *constant_expression* yeilds `false`, or the absence of an exception specification (other than for a destructor or deallocation function), indicates that the set of potential exceptions that can exit the function is the set of all types.  
 
 Mark a function as `noexcept` only if all the functions that it calls, either directly or indirectly, are also `noexcept` or `const`. The compiler does not necessarily check every code path for exceptions that might bubble up to a `noexcept` function. If an exception does exit the outer scope of a function marked `noexcept`, [std::terminate](../standard-library/exception-functions.md#terminate) is invoked immediately, and there is no guarantee that destructors of any in-scope objects will be invoked. Use `noexcept` instead of the dynamic exception specifier `throw`, which is deprecated in C++11 and later and not fully implemented in Visual Studio. We recommended you apply `noexcept` to any function that never allows an exception to propagate up the call stack. When a function is declared `noexcept`, it enables the compiler to generate more efficient code in several different contexts.    
  
## <a name="example"></a>Example  
A template function that copies its argument might be declared `noexcept` on the condition that the object being copied is a plain old data type (POD). Such a function could be declared like this:  
  
```cpp  
#include <type_traits>  
  
template <typename T>  
T copy_object(const T& obj) noexcept(std::is_pod<T>)  
{  
   // ...   
}  
```  
  
## <a name="see-also"></a>See Also  
 [C++ Exception Handling](../cpp/cpp-exception-handling.md) [Exception Specifications (throw, noexcept)](../cpp/exception-specifications-throw-cpp.md)
