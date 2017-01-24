---
title: "weibull_distribution 類別 | Microsoft Docs"
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
  - "std.tr1.weibull_distribution"
  - "weibull_distribution"
  - "tr1::weibull_distribution"
  - "std::tr1::weibull_distribution"
  - "tr1.weibull_distribution"
  - "random/std::tr1::weibull_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "weibull_distribution 類別"
ms.assetid: f20b49d3-1b9a-41af-8db4-baf800eaa02b
caps.latest.revision: 15
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# weibull_distribution 類別
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

產生 Weibull 分佈。  
  
## 語法  
  
```  
template<class RealType = double> class weibull_distribution { public:     // types     typedef RealType result_type;     struct param_type;     // constructor and reset functions     explicit weibull_distribution(RealType a = 1.0, RealType b = 1.0);     explicit weibull_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     RealType a() const;     RealType b() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### 參數  
 `RealType`  
 浮點結果類型，預設值為 `double`。  如需可能的類型，請參閱 [\<random\>](../standard-library/random.md)。  
  
## 備註  
 此範本類別描述產生使用者指定之整數類型的值的分佈 \(若無提供則為 `double` 類型\)，而這是根據 Weibull 分佈進行分佈。  下表提供各個成員的文章連結。  
  
||||  
|-|-|-|  
|[weibull\_distribution::weibull\_distribution](../Topic/weibull_distribution::weibull_distribution.md)|`weibull_distribution::a`|`weibull_distribution::param`|  
|`weibull_distribution::operator()`|`weibull_distribution::b`|[weibull\_distribution::param\_type](../Topic/weibull_distribution::param_type.md)|  
  
 屬性函式 `a()` 和 `b()` 會針對儲存的分佈參數 `a` 和 `b` 分別傳回各自的值。  
  
 如需分佈類別及其成員的詳細資訊，請參閱 [\<random\>](../standard-library/random.md)。  
  
 如需 Weibull 分佈的詳細資訊，請參閱 Wolfram MathWorld 文章：[Weibull 分佈](http://go.microsoft.com/fwlink/?LinkId=401115) \(英文\)。  
  
## 範例  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double a, const double b, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::weibull_distribution<> distr(a, b);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "a() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.a() << std::endl;  
    std::cout << "b() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.b() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<double, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        std::cout << std::fixed << std::setw(11) << ++counter << ": "  
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double a_dist = 0.0;  
    double b_dist = 1;  
  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'a' distribution parameter (must be greater than zero): ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the 'b' distribution parameter (must be greater than zero): ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
  
```  
  
## 輸出  
 第一次執行：  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter (must be greater than zero): 1  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
  
min() == 0  
max() == 1.79769e+308  
a() == 1.0000000000  
b() == 1.0000000000  
Distribution for 10 samples:  
          1:   0.0936880533  
          2:   0.1225944894  
          3:   0.6443593183  
          4:   0.6551171649  
          5:   0.7313457551  
          6:   0.7313557977  
          7:   0.7590097389  
          8:   1.4466885214  
          9:   1.6434088411  
         10:   2.1201210996  
```  
  
 第二次執行：  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter (must be greater than zero): .5  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 5.5  
Enter an integer value for the sample count: 10  
  
min() == 0  
max() == 1.79769e+308  
a() == 0.5000000000  
b() == 5.5000000000  
Distribution for 10 samples:  
          1:   0.0482759823  
          2:   0.0826617486  
          3:   2.2835941207  
          4:   2.3604817485  
          5:   2.9417663742  
          6:   2.9418471657  
          7:   3.1685268104  
          8:  11.5109922290  
          9:  14.8543594043  
         10:  24.7220241239  
```  
  
## 需求  
 **標頭：**\<random\>  
  
 **命名空間:** std  
  
## 請參閱  
 [\<random\>](../standard-library/random.md)