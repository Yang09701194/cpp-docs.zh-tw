---
title: 編譯器錯誤 C3624
ms.date: 11/04/2016
f1_keywords:
- C3624
helpviewer_keywords:
- C3624
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
ms.openlocfilehash: bb574b194f01aa1da27b962ed6be327f4f988c3c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221992"
---
# <a name="compiler-error-c3624"></a>編譯器錯誤 C3624

'type': 使用這個型別需要組件 'assembly' 的參考

未指定編譯程式碼所需的組件 （參考）;傳遞的組件[#using](../../preprocessor/hash-using-directive-cpp.md)指示詞。

## <a name="example"></a>範例

下列範例會產生 C3624:

```
// C3624.cpp
// compile with: /clr /c
#using <System.Windows.Forms.dll>

// Uncomment the following 2 lines to resolve.
// #using <System.dll>
// #using <System.Drawing.dll>

using namespace System;

public ref class MyForm : public Windows::Forms::Form {};   // C3624
```
