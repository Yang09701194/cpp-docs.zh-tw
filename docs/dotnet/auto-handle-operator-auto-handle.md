---
title: auto_handle::operator auto_handle
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr.auto_handle.operator auto_handle
- operator auto_handle
- msclr::auto_handle::operator auto_handle
- auto_handle.operator auto_handle
- auto_handle::operator auto_handle
helpviewer_keywords:
- operator auto_handle
ms.assetid: 2f8b35d1-2783-4d91-b6fb-eae551270fb8
ms.openlocfilehash: 7651d82c20e52d86acb2e41fbac2e585a3a4b75a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596205"
---
# <a name="autohandleoperator-autohandle"></a>auto_handle::operator auto_handle

之間的類型轉換運算子`auto_handle`和相容的類型。

## <a name="syntax"></a>語法

```
template<typename _other_type>
operator auto_handle<_other_type>();
```

## <a name="return-value"></a>傳回值

目前`auto_handle`轉型為`auto_handle<_other_type>`。

## <a name="example"></a>範例

```
// msl_auto_handle_op_auto_handle.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

ref class ClassA {
protected:
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ) {}

   virtual void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

ref class ClassB : ClassA {
public:
   ClassB( String ^ s) : ClassA( s ) {}
   virtual void PrintHello() new {
      Console::WriteLine( "Hello from {0} B!", m_s );
   }
};

int main() {
   auto_handle<ClassB> b = gcnew ClassB("first");
   b->PrintHello();
   auto_handle<ClassA> a = (auto_handle<ClassA>)b;
   a->PrintHello();
}
```

```Output
Hello from first B!
Hello from first A!
```

## <a name="requirements"></a>需求

**標頭檔** \<msclr\auto_handle.h >

**命名空間**msclr

## <a name="see-also"></a>另請參閱

[auto_handle 成員](../dotnet/auto-handle-members.md)