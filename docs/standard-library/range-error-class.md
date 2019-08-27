---
title: range_error 類別
ms.date: 08/14/2018
f1_keywords:
- stdexcept/std::range_error
helpviewer_keywords:
- range_error class
ms.assetid: 8afb3e88-fc49-4213-b096-ed63d7aea37c
ms.openlocfilehash: 3e741604a3bb23fa8166023d115f79e7a288e2f7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458238"
---
# <a name="rangeerror-class"></a>range_error 類別

此類別可做為擲回之所有例外狀況的基底類別，這些例外狀況報告報告範圍錯誤。

## <a name="syntax"></a>語法

```cpp
class range_error : public runtime_error {
public:
    explicit range_error(const string& message);
    explicit range_error(const char *message);
};
```

## <a name="remarks"></a>備註

[What](../standard-library/exception-class.md)所傳回的值是的複本`message.data`。 如需詳細資訊, 請參閱[basic_string::d ata](../standard-library/basic-string-class.md#data)。

## <a name="example"></a>範例

```cpp
// range_error.cpp
// compile with: /EHsc /GR
#include <iostream>
using namespace std;
int main()
{
   try
   {
      throw range_error( "The range is in error!" );
   }
   catch (range_error &e)
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught: The range is in error!
Type: class std::range_error
*/
```

## <a name="requirements"></a>需求

**標頭：** \<stdexcept>

**命名空間：** std

## <a name="see-also"></a>另請參閱

[runtime_error 類別](../standard-library/runtime-error-class.md)\
[C++ 標準程式庫中的執行緒安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
