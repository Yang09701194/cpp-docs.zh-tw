---
title: 編譯器錯誤 C3702 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3702
dev_langs:
- C++
helpviewer_keywords:
- C3702
ms.assetid: 14fcc20e-4404-45d7-be54-e4f09332fa5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0267b549e50537c5122ddd0bb652b9c64f2943fd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047085"
---
# <a name="compiler-error-c3702"></a>編譯器錯誤 C3702

'function': ATL 做是為了 COM 事件

您嘗試使用不含必要的 ATL 標頭檔的 COM 事件。

下列範例會產生 C3702:

```
// C3702.cpp
// uncomment the following line to resolve
// #define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(dll, name=idid, uuid="12341234-1234-1234-1234-123412341234")];

[object]
__interface IEvents : IUnknown
{
   HRESULT event1([in] int i);
};

[dual]
__interface IBase
{
   HRESULT fireEvents();
};

[coclass, event_source(com)]
class CEventSrc : public IBase
{
   public:
   __event __interface IEvents;

   HRESULT fireEvents()
   {
      HRESULT hr = IEvents_event1(123);
      return hr;
   }
};   // C3702

int main() {
}
```