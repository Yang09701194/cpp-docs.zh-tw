---
title: binomial_distribution 類別
ms.date: 11/04/2016
f1_keywords:
- random/std::binomial_distribution
- random/std::binomial_distribution::reset
- random/std::binomial_distribution::p
- random/std::binomial_distribution::t
- random/std::binomial_distribution::param
- random/std::binomial_distribution::min
- random/std::binomial_distribution::max
- random/std::binomial_distribution::operator()
- random/std::binomial_distribution::param_type
- random/std::binomial_distribution::param_type::p
- random/std::binomial_distribution::param_type::t
- random/std::binomial_distribution::param_type::operator==
- random/std::binomial_distribution::param_type::operator!=
helpviewer_keywords:
- std::binomial_distribution [C++]
- std::binomial_distribution [C++], reset
- std::binomial_distribution [C++], p
- std::binomial_distribution [C++], t
- std::binomial_distribution [C++], param
- std::binomial_distribution [C++], min
- std::binomial_distribution [C++], max
- std::binomial_distribution [C++], param_type
- std::binomial_distribution [C++], param_type
ms.assetid: b7c8a26a-da8c-45a5-a3a8-208f7a3609ce
ms.openlocfilehash: dc9bb1c3edf9187b1e5dc1e924298b9dbb02e2ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376718"
---
# <a name="binomial_distribution-class"></a>binomial_distribution 類別

產生二項式分佈。

## <a name="syntax"></a>語法

```cpp
template<class IntType = int>
class binomial_distribution
   {
public:
   // types
   typedef IntType result_type;
   struct param_type;

   // constructors and reset functions
   explicit binomial_distribution(result_type t = 1, double p = 0.5);
   explicit binomial_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   result_type t() const;
   double p() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>參數

*IntType*\
整數結果類型,預設值為**int**。有關可能的類型,請參閱[\<隨機>](../standard-library/random.md)。

*烏爾格*\
統一的隨機數生成器引擎。 有關可能的類型,請參閱[\<隨機>](../standard-library/random.md)。

## <a name="remarks"></a>備註

類範本描述生成使用者指定積分類型的值的分佈,或者如果沒有提供,則類型**int,** 根據二元分布離散概率函數進行分佈。 下表提供各個成員的文章連結。

||||
|-|-|-|
|[binomial_distribution](#binomial_distribution)|`binomial_distribution::t`|`binomial_distribution::param`|
|`binomial_distribution::operator()`|`binomial_distribution::p`|[param_type](#param_type)|

屬性成員`t()``p()`並分別返回當前存儲的分布參數值*t*和*p。*

屬性成員 `param()` 會設定或傳回 `param_type` 預存的分佈參數套件。

`min()` 和 `max()` 成員函式會分別傳回最小可能結果和最大可能結果。

`reset()` 成員函式會捨棄任何快取的值，讓下個針對 `operator()` 呼叫的結果不是取決於呼叫之前取自引擎的任何值。

`operator()` 成員函式會根據 URNG 引擎傳回下一個產生的值，無論是從目前的參數封裝或是指定的參數封裝。

有關分發類及其成員的詳細資訊,請參閱[\<隨機>](../standard-library/random.md)。

如需二項式分佈離散機率函式的詳細資訊，請參閱 Wolfram MathWorld 文章：[Binomial Distribution](https://go.microsoft.com/fwlink/p/?linkid=398469) (二項式分佈)。

## <a name="example"></a>範例

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const int t, const double p, const int& s) {

    // uncomment to use a non-deterministic seed
    //    std::random_device rd;
    //    std::mt19937 gen(rd());
    std::mt19937 gen(1729);

    std::binomial_distribution<> distr(t, p);

    std::cout << std::endl;
    std::cout << "p == " << distr.p() << std::endl;
    std::cout << "t == " << distr.t() << std::endl;

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
    int    t_dist = 1;
    double p_dist = 0.5;
    int    samples = 100;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter an integer value for t distribution (where 0 <= t): ";
    std::cin >> t_dist;
    std::cout << "Enter a double value for p distribution (where 0.0 <= p <= 1.0): ";
    std::cin >> p_dist;
    std::cout << "Enter an integer value for a sample count: ";
    std::cin >> samples;

    test(t_dist, p_dist, samples);
}
```

第一次執行：

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for t distribution (where 0 <= t): 22
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .25
Enter an integer value for a sample count: 100

p == 0.25
t == 22
Histogram for 100 samples:
    1 :
    2 ::
    3 :::::::::::::
    4 ::::::::::::::
    5 :::::::::::::::::::::::::
    6 ::::::::::::::::::
    7 :::::::::::::
    8 ::::::
    9 ::::::
    11 :
    12 :
```

第二次執行：

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for t distribution (where 0 <= t): 22
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .5
Enter an integer value for a sample count: 100

p == 0.5
t == 22
Histogram for 100 samples:
    6 :
    7 ::
    8 :::::::::
    9 ::::::::::
    10 ::::::::::::::::
    11 :::::::::::::::::::
    12 :::::::::::
    13 :::::::::::::
    14 :::::::::::::::
    15 ::
    16 ::
```

第三次執行：

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for t distribution (where 0 <= t): 22
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .75
Enter an integer value for a sample count: 100

p == 0.75
t == 22
Histogram for 100 samples:
    13 ::::
    14 :::::::::::
    15 :::::::::::::::
    16 :::::::::::::::::::::
    17 ::::::::::::::
    18 :::::::::::::::::
    19 :::::::::::
    20 ::::::
    21 :
```

## <a name="requirements"></a>需求

**標頭：** \<random>

**命名空間：** std

## <a name="binomial_distributionbinomial_distribution"></a><a name="binomial_distribution"></a>binomial_distribution:binomial_distribution

建構分佈。

```cpp
explicit binomial_distribution(result_type t = 1, double p = 0.5);
explicit binomial_distribution(const param_type& parm);
```

### <a name="parameters"></a>參數

*t*\
`t` 分佈參數。

*P*\
`p` 分佈參數。

*帕爾姆*\
用來建構分佈的 `param_type` 結構。

### <a name="remarks"></a>備註

**前置條件：** `0 ≤ t` 和 `0.0 ≤ p ≤ 1.0`

第一個建構函式建構一個物件的儲存*p*值包含值*p,* 其儲存*t*值包含值*t*。

第二個建構函式會建構預存參數是從 *parm* 初始化而來的物件。 您可以呼叫 `param()` 成員函式，取得及設定現有分佈的目前參數。

## <a name="binomial_distributionparam_type"></a><a name="param_type"></a>binomial_distribution::p阿拉姆型

儲存分佈的所有參數。

```cpp
struct param_type {
   typedef binomial_distribution<result_type> distribution_type;
   param_type(result_type t = 1, double p = 0.5);
   result_type t() const;
   double p() const;
   .....
   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>參數

*t*\
`t` 分佈參數。

*P*\
`p` 分佈參數。

*對*\
要與這個項目比較的 `param_type` 物件。

### <a name="remarks"></a>備註

**前置條件：** `0 ≤ t` 和 `0.0 ≤ p ≤ 1.0`

此結構可在具現化時傳遞至分佈的類別建構函式，傳遞至 `param()` 成員函式可設定現有分佈之儲存的參數，傳遞至 `operator()` 可用於取代儲存的參數。

## <a name="see-also"></a>另請參閱

[\<隨機>](../standard-library/random.md)
