---
title: "negative_binomial_distribution 類別 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::negative_binomial_distribution
- random/std::negative_binomial_distribution::reset
- random/std::negative_binomial_distribution::k
- random/std::negative_binomial_distribution::p
- random/std::negative_binomial_distribution::param
- random/std::negative_binomial_distribution::min
- random/std::negative_binomial_distribution::max
- random/std::negative_binomial_distribution::operator()
- random/std::negative_binomial_distribution::param_type
- random/std::negative_binomial_distribution::param_type::k
- random/std::negative_binomial_distribution::param_type::p
- random/std::negative_binomial_distribution::param_type::operator==
- random/std::negative_binomial_distribution::param_type::operator!=
dev_langs: C++
helpviewer_keywords:
- std::negative_binomial_distribution [C++]
- std::negative_binomial_distribution [C++], reset
- std::negative_binomial_distribution [C++], k
- std::negative_binomial_distribution [C++], p
- std::negative_binomial_distribution [C++], param
- std::negative_binomial_distribution [C++], min
- std::negative_binomial_distribution [C++], max
- std::negative_binomial_distribution [C++], param_type
- std::negative_binomial_distribution [C++], param_type
ms.assetid: 7f5f0967-7fdd-4578-99d4-88f292b4fe9c
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea765a3a6f0b7d713b0807129d04cc9b8653951b
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/03/2018
---
# <a name="negativebinomialdistribution-class"></a>negative_binomial_distribution 類別
產生負二項式分佈。  
  
## <a name="syntax"></a>語法  
  
```
template<class IntType = int>
class negative_binomial_distribution
{
public:
    // types 
    typedef IntType result_type;
    struct param_type;   
    
    // constructor and reset functions
    explicit negative_binomial_distribution(result_type k = 1, double p = 0.5);
    explicit negative_binomial_distribution(const param_type& parm);
    void reset();
    
    // generating functions 
    template `<`class URNG>  
    result_type operator()(URNG& gen);
    template `<`class URNG>
    result_type operator()(URNG& gen, const param_type& parm);
    
    // property functions     
    result_type k() const;
    double p() const;
    param_type param() const;
    void param(const param_type& parm);
    result_type min() const;
    result_type max() const; 
};
  
### Parameters  
*IntType*  
The integer result type, defaults to `int`. For possible types, see [\<random>](../standard-library/random.md).  
  
## Remarks  
The template class describes a distribution that produces values of a user-specified integral type, or type `int` if none is provided, distributed according to the Negative Binomial Distribution discrete probability function. The following table links to articles about individual members.  
  
||||  
|-|-|-|  
|[negative_binomial_distribution](#negative_binomial_distribution)|`negative_binomial_distribution::k`|`negative_binomial_distribution::param`|  
|`negative_binomial_distribution::operator()`|`negative_binomial_distribution::p`|[param_type](#param_type)|  
  
The property members `k()` and `p()` return the currently stored distribution parameter values *k* and *p* respectively.  
  
The property member `param()` sets or returns the `param_type` stored distribution parameter package.  

The `min()` and `max()` member functions return the smallest possible result and largest possible result, respectively.  
  
The `reset()` member function discards any cached values, so that the result of the next call to `operator()` does not depend on any values obtained from the engine before the call.  
  
The `operator()` member functions return the next generated value based on the URNG engine, either from the current parameter package, or the specified parameter package.
  
For more information about distribution classes and their members, see [\<random>](../standard-library/random.md).  
  
For detailed information about the negative binomial distribution discrete probability function, see the Wolfram MathWorld article [Negative Binomial Distribution](http://go.microsoft.com/fwlink/p/?linkid=400516).  
  
## Example  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const int k, const double p, const int& s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::negative_binomial_distribution<> distr(k, p);  
  
    std::cout << std::endl;  
    std::cout << "k == " << distr.k() << std::endl;  
    std::cout << "p == " << distr.p() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Histogram for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    int    k_dist = 1;  
    double p_dist = 0.5;  
    int    samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter an integer value for k distribution (where 0 < k): ";  
    std::cin >> k_dist;  
    std::cout << "Enter a double value for p distribution (where 0.0 < p <= 1.0): ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for a sample count: ";  
    std::cin >> samples;  
  
    test(k_dist, p_dist, samples);  
}  
  
```  
  
第一次執行：  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for k distribution (where 0 `<` k): 1  
Enter a double value for p distribution (where 0.0 `<`p `<`= 1.0): .5  
Enter an integer value for a sample count: 100  
 
k == 1  
p == 0.5  
Histogram for 100 samples:  
    0 :::::::::::::::::::::::::::::::::::::::::::  
    1 ::::::::::::::::::::::::::::::::  
    2 ::::::::::::  
    3 :::::::  
    4 ::::  
    5 ::  
```  
  
第二次執行：  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for k distribution (where 0 `<` k): 100  
Enter a double value for p distribution (where 0.0 `<` p <= 1.0): .667  
Enter an integer value for a sample count: 100  
 
k == 100  
p == 0.667  
Histogram for 100 samples:  
    31 ::  
    32 :  
    33 ::  
    34 :  
    35 ::  
    37 ::  
    38 :  
    39 :  
    40 ::  
    41 :::  
    42 :::  
    43 :::::  
    44 :::::  
    45 ::::  
    46 ::::::  
    47 ::::::::  
    48 :::  
    49 :::  
    50 :::::::::  
    51 :::::::  
    52 ::  
    53 :::  
    54 :::::  
    56 ::::  
    58 :  
    59 :::::  
    60 ::  
    61 :  
    62 ::  
    64 :  
    69 ::::  
```  
  
## <a name="requirements"></a>需求  
**標頭：**\<random>  
  
**命名空間：** std  
  
##  <a name="negative_binomial_distribution"></a>  negative_binomial_distribution::negative_binomial_distribution  
建構分佈。  
  
```  
explicit negative_binomial_distribution(result_type k = 1, double p = 0.5);
explicit negative_binomial_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>參數  
*k*  
`k` 分佈參數。  
  
*p*  
`p` 分佈參數。  
  
*parm*  
用於建構分佈的參數結構。  
  
### <a name="remarks"></a>備註  
**前置條件：**`0.0 < k` 和 `0.0 < p ≤ 1.0`  
  
第一個建構函式會建構預存 `p` 值具有 *p* 值而預存 `k` 值具有 *k* 值的物件。  
  
第二個建構函式會建構預存參數是從 *parm* 初始化而來的物件。 您可以呼叫 `param()` 成員函式，取得及設定現有分佈的目前參數。  
  
##  <a name="param_type"></a>  negative_binomial_distribution::param_type  
儲存分佈的參數。  
  
struct param_type {  
   typedef negative_binomial_distribution`<`result_type> distribution_type;  
   param_type(result_type k = 1, double p = 0.5); result_type k() const; double p() const;

   bool operator==(const param_type& right) const; bool operator!=(const param_type& right) const; };  
  
### <a name="parameters"></a>參數  
*k*  
`k` 分佈參數。  
  
*p*  
`p` 分佈參數。  
  
*right*  
用來進行比較的 `param_type` 結構。  
  
### <a name="remarks"></a>備註  
**前置條件：**`0.0 < k` 和 `0.0 < p ≤ 1.0`  
  
此結構可在具現化時傳遞至分佈的類別建構函式，傳遞至 `param()` 成員函式可設定現有分佈之儲存的參數，傳遞至 `operator()` 可用於取代儲存的參數。  
  
## <a name="see-also"></a>請參閱  
 [\<random>](../standard-library/random.md)
