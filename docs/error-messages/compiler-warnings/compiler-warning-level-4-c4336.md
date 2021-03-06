---
title: 編譯器警告 (層級 4) C4336
ms.date: 11/04/2016
f1_keywords:
- C4336
helpviewer_keywords:
- C4336
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
ms.openlocfilehash: e83bac9028980bdf3ef7449fbef065a8c9316d2d
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991330"
---
# <a name="compiler-warning-level-4-c4336"></a>編譯器警告 (層級 4) C4336

匯入 ' type_lib2 ' 之前，請先匯入交叉參考的類型程式庫 ' type_lib1 '

已使用[#import](../../preprocessor/hash-import-directive-cpp.md)指示詞參考類型程式庫。 不過，類型程式庫包含另一個未使用 `#import`參考的類型程式庫參考。 編譯器發現這個其他 .tlb 檔案。

從下列兩個檔案（以 midl 編譯）所建立的磁片上，指定了兩個類型程式庫：

```
// c4336a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library c4336aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]
   enum E_C4336
   {
      one, two, three
   };
};
```

第二個類型程式庫：

```
// c4336b.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
library C4336bLib
{
   importlib ("c4336a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
   struct S_C4336
   {
      enum E_C4336 e;
   };
};
```

下列範例會產生 C4336：

```cpp
// C4336.cpp
// compile with: /W4 /LD
// #import "C4336a.tlb"
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve
```
