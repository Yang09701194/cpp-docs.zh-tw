---
title: "common_type 類別 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.common_type"
  - "common_type"
  - "std::tr1::common_type"
  - "std.common_type"
  - "std::common_type"
  - "type_traits/std::common_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "common_type 類別 [TR1]"
  - "common_type"
ms.assetid: 02bc4e7b-c63d-49de-9f8a-511d3a5c1e7f
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# common_type 類別
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

判斷一或多個類型的一般類型。  
  
## 語法  
  
```  
  
template <class... T>  
   struct common_type;  
  
template <class T>  
   struct common_type<T> {  
      typedef typename decay<T>::type type;  
};  
  
template <class T, class U>  
   struct common_type<T, U> {  
      typedef typename decay<decltype(true ?  declval<T>() :  
         declval<U>())>::type type;  
};  
  
template <class T, class U, class... V>  
   struct common_type<T, U, V...> {  
      typedef typename common_type<typename common_type<T, U>::type, V...>::type type;  
};  
```  
  
#### 參數  
 類型清單為[完成類型](../c-language/incomplete-types.md)或 void。  
  
## 備註  
 `type` 成員是常見的類型，其中參數清單中的所有類型都可以轉換為該類型。  
  
## 範例  
 下列程式會示範一些正確使用方式案例和測試以取得結果。  
  
```cpp  
// Compile using cl.exe /EHsc  
// common_type sample  
#include <iostream>  
#include <type_traits>  
  
struct Base {};  
struct Derived : Base {};  
  
int main()   
{  
    typedef std::common_type<unsigned char, short, int>::type NumericType;  
    typedef std::common_type<float, double>::type FloatType;  
    typedef std::common_type<const int, volatile int>::type ModifiedIntType;  
    typedef std::common_type<Base, Derived>::type ClassType;  
  
    std::cout << std::boolalpha;  
    std::cout << "Test for typedefs of common_type int" << std::endl;  
    std::cout << "NumericType: "     << std::is_same<int, NumericType>::value << std::endl;  
    std::cout << "FloatType: "       << std::is_same<int, FloatType>::value << std::endl;  
    std::cout << "ModifiedIntType: " << std::is_same<int, ModifiedIntType>::value << std::endl;  
    std::cout << "ClassType: "       << std::is_same<int, ClassType>::value << std::endl;  
    std::cout << "---------------------------" << std::endl;  
    std::cout << "Test for typedefs of common_type double" << std::endl;  
    std::cout << "NumericType: "     << std::is_same<double, NumericType>::value << std::endl;  
    std::cout << "FloatType: "       << std::is_same<double, FloatType>::value << std::endl;  
    std::cout << "ModifiedIntType: " << std::is_same<double, ModifiedIntType>::value << std::endl;  
    std::cout << "ClassType: "       << std::is_same<double, ClassType>::value << std::endl;  
    std::cout << "---------------------------" << std::endl;  
    std::cout << "Test for typedefs of common_type Base" << std::endl;  
    std::cout << "NumericType: "     << std::is_same<Base, NumericType>::value << std::endl;  
    std::cout << "FloatType: "       << std::is_same<Base, FloatType>::value << std::endl;  
    std::cout << "ModifiedIntType: " << std::is_same<Base, ModifiedIntType>::value << std::endl;  
    std::cout << "ClassType: "       << std::is_same<Base, ClassType>::value << std::endl;  
  
    return 0;  
}  
```  
  
## 輸出  
  
```  
Test for typedefs of common_type int  
NumericType: true  
FloatType: false  
ModifiedIntType: true  
ClassType: false  
---------------------------  
Test for typedefs of common_type double  
NumericType: false  
FloatType: true  
ModifiedIntType: false  
ClassType: false  
---------------------------  
Test for typedefs of common_type Base  
NumericType: false  
FloatType: false  
ModifiedIntType: false  
ClassType: true  
  
```  
  
## 需求  
 **標頭：**\<type\_traits\>  
  
 **命名空間:** std  
  
## 請參閱  
 [\<type\_traits\>](../standard-library/type-traits.md)