---
title: 編譯器錯誤 C3508
ms.date: 11/04/2016
f1_keywords:
- C3508
helpviewer_keywords:
- C3508
ms.assetid: 16d08f89-2f32-44eb-9421-68acecddf49b
ms.openlocfilehash: 1d868a8f7ab8a69054844c5c8e101d661e295a37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187361"
---
# <a name="compiler-error-c3508"></a>編譯器錯誤 C3508

'type': 不是有效的 Automation 類型

指定了無效的類型。

## <a name="example"></a>範例

下列範例會產生 C3508:

```
// C3508.cpp
#define _ATL_DEBUG_QI

#define WIN32_LEAN_AND_MEAN
#define STRICT
#ifndef _WIN32_WINNT
#define _WIN32_WINNT 0x0400
#endif

#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
extern CComModule _Module;
#include <atlcom.h>
#include <atlctl.h>
#include <atlstr.h>

extern "C" int printf_s(const char*, ...);

[module(name=oso)];

union U
// try the following two lines instead
// [export]
// struct U
{
   int i, j;
};

[dispinterface]
__interface I
{
   [id(1)] HRESULT func(U* u);
};

[coclass]
struct C : I
{
   HRESULT func(U*)   // C3508
   {
      return E_FAIL;
   }
};

int main()
{
}
```