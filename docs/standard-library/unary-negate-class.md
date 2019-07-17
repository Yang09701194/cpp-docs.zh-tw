---
title: unary_negate 類別
ms.date: 02/21/2019
f1_keywords:
- functional/std::unary_negate
helpviewer_keywords:
- unary_negate class
ms.assetid: e3b86eec-3205-49b9-ab83-f55225af4e0c
ms.openlocfilehash: 2a7ce9a8593b0dd93b1c3cfe58f2d87fe10ea997
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240538"
---
# <a name="unarynegate-class"></a>unary_negate 類別

提供一個成員函式的樣板類別，這個成員函式可將指定一元函式的傳回值變成負值。 支持的 C + + 17 中已被取代[not_fn](functional-functions.md#not_fn)。

## <a name="syntax"></a>語法

```cpp
template <class Predicate>
class unary_negate
    : public unaryFunction<typename Predicate::argument_type, bool>
{
    explicit unary_negate(const Predicate& Func);
    bool operator()(const typename Predicate::argument_type& left) const;
};
```

### <a name="parameters"></a>參數

*函式*\
要變為負值的一元函式。

*左邊*\
要變為負值之一元函式的運算元。

## <a name="return-value"></a>傳回值

一元函式的負運算。

## <a name="remarks"></a>備註

此範本類別會儲存一元函式物件的複本 *\_Func*。 它會定義其成員函式`operator()`做為傳回`!_Func(left)`。

`unary_negate` 的建構函式很少會直接使用。 Helper 函式 [not1](../standard-library/functional-functions.md#not1) 提供宣告和使用 **unary_negator** 配接器述詞的更簡易方式。

## <a name="example"></a>範例

```cpp
// functional_unary_negate.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 7; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    // Count the elements greater than 10
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    vector<int>::iterator::difference_type result2;
    // Use the negator to count the elements less than or equal to 10
    result2 = count_if(v1.begin(), v1.end(),
        unary_negate<binder2nd <greater<int> > >(bind2nd(greater<int>(),10)));

    // The following helper function not1 also works for the above line
    // not1(bind2nd(greater<int>(), 10)));

    cout << "The number of elements in v1 not greater than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
```
