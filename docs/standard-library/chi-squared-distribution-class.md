---
title: "chi_squared_distribution 類別 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::chi_squared_distribution"
  - "chi_squared_distribution"
  - "random/std::tr1::chi_squared_distribution"
  - "std.tr1.chi_squared_distribution"
  - "tr1.chi_squared_distribution"
  - "tr1::chi_squared_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "chi_squared_distribution 類別"
ms.assetid: 9b603fbe-cafd-4a92-b8c5-a434d60b8122
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# chi_squared_distribution 類別
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

產生卡方分佈。  
  
## 語法  
  
```  
template<class RealType = double> class chi_squared_distribution { public:     // types     typedef RealType result_type;     struct param_type;     // constructor and reset functions     explicit chi_squared_distribution(RealType n = 1);     explicit chi_squared_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     RealType n() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### 參數  
 `RealType`  
 浮點結果類型，預設值為 `double`。  如需可能的類型，請參閱 [\<random\>](../standard-library/random.md)。  
  
## 備註  
 此範本類別描述產生使用者指定之整數類型的值的分佈 \(若無提供則為 `double` 類型\)，而這是根據卡方分佈進行分佈。  下表提供各個成員的文章連結。  
  
||||  
|-|-|-|  
|[chi\_squared\_distribution::chi\_squared\_distribution](../standard-library/chi-squared-distribution-class.md)|`chi_squared_distribution::n`|`chi_squared_distribution::param`|  
|`chi_squared_distribution::operator()`||[chi\_squared\_distribution::param\_type](../Topic/chi_squared_distribution::param_type.md)|  
  
 屬性函式 `n()` 會傳回儲存的分佈參數 `n` 的值。  
  
 如需分佈類別及其成員的詳細資訊，請參閱 [\<random\>](../standard-library/random.md)。  
  
 如需卡方分佈的詳細資訊，請參閱 Wolfram MathWorld 文章：[卡方分佈](http://go.microsoft.com/fwlink/?LinkId=400528) \(英文\)。  
  
## 範例  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double n, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::chi_squared_distribution<> distr(n);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "n() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.n() << std::endl;  
  
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
    double n_dist = 0.5;  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the \'n\' distribution parameter (must be greater than zero): ";  
    std::cin >> n_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(n_dist, samples);  
}  
  
```  
  
## 輸出  
 第一次執行：  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): .5  
Enter an integer value for the sample count: 10  
  
min() == 4.94066e-324  
max() == 1.79769e+308  
n() == 0.5000000000  
Distribution for 10 samples:  
          1:   0.0007625595  
          2:   0.0016895062  
          3:   0.0058683478  
          4:   0.0189647765  
          5:   0.0556619371  
          6:   0.1448191353  
          7:   0.1448245325  
          8:   0.1903494379  
          9:   0.9267525768  
         10:   1.5429743723  
```  
  
 第二次執行：  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): .3333  
Enter an integer value for the sample count: 10  
  
min() == 4.94066e-324  
max() == 1.79769e+308  
n() == 0.3333000000  
Distribution for 10 samples:  
          1:   0.0000148725  
          2:   0.0000490528  
          3:   0.0003175988  
          4:   0.0018454535  
          5:   0.0092808795  
          6:   0.0389540735  
          7:   0.0389562514  
          8:   0.0587028468  
          9:   0.6183666639  
         10:   1.3552086624  
```  
  
 第三次執行：  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): 1000  
Enter an integer value for the sample count: 10  
  
min() == 4.94066e-324  
max() == 1.79769e+308  
n() == 1000.0000000000  
Distribution for 10 samples:  
          1: 958.5284624473  
          2: 958.7882787809  
          3: 963.0667684792  
          4: 987.9638091514  
          5: 1016.2433493745  
          6: 1021.9337111110  
          7: 1021.9723046240  
          8: 1035.7622110505  
          9: 1043.8725156645  
         10: 1054.7051509381  
```  
  
## 需求  
 **標頭：**\<random\>  
  
 **命名空間:** std  
  
## 請參閱  
 [\<random\>](../standard-library/random.md)