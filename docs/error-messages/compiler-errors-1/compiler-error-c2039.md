---
title: 編譯器錯誤 C2039
ms.date: 11/04/2016
f1_keywords:
- C2039
helpviewer_keywords:
- C2039
ms.assetid: f9dfd521-9b36-4454-a69c-d63f45b606bb
ms.openlocfilehash: 67c64de676c624369fb5a8bc07b9b5de4833fe7f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757679"
---
# <a name="compiler-error-c2039"></a>編譯器錯誤 C2039

' identifier1 '：不是 ' identifier2 ' 的成員

程式碼不正確地呼叫或參考結構、類別或等位的成員。

## <a name="example"></a>範例

下列範例會產生 C2039。

```cpp
// C2039.cpp
struct S {
   int mem0;
} s, *pS = &s;

int main() {
   pS->mem1 = 0;   // C2039 mem1 is not a member
   pS->mem0 = 0;   // OK
}
```

## <a name="example"></a>範例

下列範例會產生 C2039。

```cpp
// C2039_b.cpp
// compile with: /clr
using namespace System;
int main() {
   Console::WriteLine( "{0}", DateTime::get_Now());   // C2039
   Console::WriteLine( "{0}", DateTime::Now);   // OK
   Console::WriteLine( "{0}", DateTime::Now::get());   // OK
}
```

## <a name="example"></a>範例

下列範例會產生 C2039。

```cpp
// C2039_c.cpp
// compile with: /clr /c
ref struct S {
   property int Count {
     int get();
     void set(int i){}
   };
};

int S::get_Count() { return 0; }   // C2039
int S::Count::get() { return 0; }   // OK
```

## <a name="example"></a>範例

如果您嘗試不正確地存取預設索引子，也可能會發生 C2039。 下列範例會定義在中C#撰寫的元件。

```
// C2039_d.cs
// compile with: /target:library
// a C# program
[System.Reflection.DefaultMember("Item")]
public class B {
   public int Item {
      get { return 13; }
      set {}
   }
};
```

## <a name="example"></a>範例

下列範例會產生 C2039。

```cpp
// C2039_e.cpp
// compile with: /clr
using namespace System;
#using "c2039_d.dll"

int main() {
   B ^ b = gcnew B;
   int n = b->default;   // C2039
   // try the following line instead
   // int n = b->Item;
   Console::WriteLine(n);
}
```

## <a name="example"></a>範例

如果您使用泛型，也可能會發生 C2039。 下列範例會產生 C2039。

```cpp
// C2039_f.cpp
// compile with: /clr
interface class I {};

ref struct R : public I {
   virtual void f3() {}
};

generic <typename T>
where T : I
void f(T t) {
   t->f3();   // C2039
   safe_cast<R^>(t)->f3();   // OK
}

int main() {
   f(gcnew R());
}
```

## <a name="example"></a>範例

當您嘗試釋放受控或非受控資源時，可能會發生 C2039。 如需詳細資訊，請參閱[析構函數和](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)完成項。

下列範例會產生 C2039。

```cpp
// C2039_g.cpp
// compile with: /clr
using namespace System;
using namespace System::Threading;

void CheckStatus( Object^ stateInfo ) {}

int main() {
   ManualResetEvent^ event = gcnew ManualResetEvent( false );
   TimerCallback^ timerDelegate = gcnew TimerCallback( &CheckStatus );
   Timer^ stateTimer = gcnew Timer( timerDelegate, event, 1000, 250 );

   ((IDisposable ^)stateTimer)->Dispose();   // C2039

   stateTimer->~Timer();   // OK
}
```
