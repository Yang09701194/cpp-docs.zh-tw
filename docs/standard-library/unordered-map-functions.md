---
title: '&lt;unordered_map&gt; 函式'
ms.date: 11/04/2016
f1_keywords:
- unordered_map/std::swap
- unordered_map/std::swap (unordered_map)
- unordered_map/std::swap (unordered_multimap)
ms.assetid: cf2e4115-f205-4a0e-90be-a143ffcc1f44
helpviewer_keywords:
- std::swap (unordered_map/multimap)
ms.openlocfilehash: ae00a9204e2bd5dc5220f3b2755e16b895193df3
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517942"
---
# <a name="ltunorderedmapgt-functions"></a>&lt;unordered_map&gt; 函式

|||
|-|-|
|[swap (unordered_map)](#swap)|[swap (unordered_multimap)](#swap_function_multimap)|

## <a name="swap"></a>  swap (unordered_map)

交換兩個容器的內容。

```cpp
template <class Key, class Ty, class Hash, class Pred, class Alloc>
void swap(
    unordered_map <Key, Ty, Hash, Pred, Alloc>& left,
    unordered_map <Key, Ty, Hash, Pred, Alloc>& right);
```

### <a name="parameters"></a>參數

*Key*<br/>
索引鍵類型。

*Ty*<br/>
對應的類型。

*雜湊*<br/>
雜湊函式物件類型。

*預測*<br/>
相等比較函式物件類型。

*配置*<br/>
配置器類別。

*left*<br/>
要交換的第一個容器。

*right*<br/>
要交換的第二個容器。

### <a name="remarks"></a>備註

範本函式執行 `left.`[unordered_map::swap](../standard-library/unordered-map-class.md#swap)`(right)`。

### <a name="example"></a>範例

```cpp
// std__unordered_map__u_m_swap.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    Mymap c2;

    c2.insert(Mymap::value_type('d', 4));
    c2.insert(Mymap::value_type('e', 5));
    c2.insert(Mymap::value_type('f', 6));

    c1.swap(c2);

// display contents " [f 6] [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    swap(c1, c2);

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }
```

```Output
[c, 3] [b, 2] [a, 1]
[f, 6] [e, 5] [d, 4]
[c, 3] [b, 2] [a, 1]
```

## <a name="swap_function_multimap"></a>  swap (unordered_multimap)

交換兩個容器的內容。

```cpp
template <class Key, class Ty, class Hash, class Pred, class Alloc>
void swap(
    unordered_multimap <Key, Ty, Hash, Pred, Alloc>& left,
    unordered_multimap <Key, Ty, Hash, Pred, Alloc>& right);
```

### <a name="parameters"></a>參數

*Key*<br/>
索引鍵類型。

*Ty*<br/>
對應的類型。

*雜湊*<br/>
雜湊函式物件類型。

*預測*<br/>
相等比較函式物件類型。

*配置*<br/>
配置器類別。

*left*<br/>
要交換的第一個容器。

*right*<br/>
要交換的第二個容器。

### <a name="remarks"></a>備註

範本函式執行 `left.`[unordered_multimap::swap](../standard-library/unordered-multimap-class.md#swap)`(right)`。

### <a name="example"></a>範例

```cpp
// std__unordered_map__u_mm_swap.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
{
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

    // display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    Mymap c2;

    c2.insert(Mymap::value_type('d', 4));
    c2.insert(Mymap::value_type('e', 5));
    c2.insert(Mymap::value_type('f', 6));

    c1.swap(c2);

    // display contents " [f 6] [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    swap(c1, c2);

    // display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c, 3] [b, 2] [a, 1]
[f, 6] [e, 5] [d, 4]
[c, 3] [b, 2] [a, 1]
```

## <a name="see-also"></a>另請參閱

[<unordered_map>](../standard-library/unordered-map.md)<br/>
