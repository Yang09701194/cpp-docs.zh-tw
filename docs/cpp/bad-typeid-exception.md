---
title: bad_typeid 例外狀況
ms.date: 10/04/2019
f1_keywords:
- bad_typeid
- bad_typeid_cpp
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
ms.openlocfilehash: bb56de77ba001b5a511ef3a2695d18109b1ed3ca
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245922"
---
# <a name="bad_typeid-exception"></a>bad_typeid 例外狀況

The **bad_typeid** exception is thrown by the [typeid operator](../cpp/typeid-operator.md) when the operand for **typeid** is a NULL pointer.

## <a name="syntax"></a>語法

```
catch (bad_typeid)
   statement
```

## <a name="remarks"></a>備註

The interface for **bad_typeid** is:

```cpp
class bad_typeid : public exception
{
public:
   bad_typeid();
   bad_typeid(const char * _Message = "bad typeid");
   bad_typeid(const bad_typeid &);
   virtual ~bad_typeid();

   bad_typeid& operator=(const bad_typeid&);
   const char* what() const;
};
```

The following example shows the **typeid** operator throwing a **bad_typeid** exception.

```cpp
// expre_bad_typeid.cpp
// compile with: /EHsc /GR
#include <typeinfo>
#include <iostream>

class A{
public:
   // object for class needs vtable
   // for RTTI
   virtual ~A();
};

using namespace std;
int main() {
A* a = NULL;

try {
   cout << typeid(*a).name() << endl;  // Error condition
   }
catch (bad_typeid){
   cout << "Object is NULL" << endl;
   }
}
```

## <a name="output"></a>Output

```Output
Object is NULL
```

## <a name="see-also"></a>請參閱

[執行階段類型資訊](../cpp/run-time-type-information.md)\
[關鍵字](../cpp/keywords-cpp.md)
