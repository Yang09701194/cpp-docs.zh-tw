---
title: 編譯器錯誤 C2752 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2752
dev_langs:
- C++
helpviewer_keywords:
- C2752
ms.assetid: ae42b3ec-84a9-4e9d-8d59-3d208132d0b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea33ef80847a8699115a92e316fec156c3c51607
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081646"
---
# <a name="compiler-error-c2752"></a>編譯器錯誤 C2752

'template': 一個以上的部分特製化符合樣板引數清單

具現化模稜兩可。

下列範例會產生 C2752:

```
// C2752.cpp
template<class T, class U>
struct A {};

template<class T, class U>
struct A<T*, U> {};

template<class T, class U>
struct A<T,U*> {};

// try the following line instead
// template<class T, class U> struct A<T*,U*> {};

int main() {
   A<char*,int*> a;   // C2752 an instantiation

   // OK
   A<char*,int> a1;
   A<char,int*> a2;
   A<char,int> a3;
}
```