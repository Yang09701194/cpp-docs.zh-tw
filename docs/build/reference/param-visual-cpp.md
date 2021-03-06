---
title: '&lt;param > (C++文件註解)'
ms.date: 11/04/2016
f1_keywords:
- param
- <param>
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
ms.openlocfilehash: d8ea4feddbe1ec2d5898f8ef698cc2d69d255933
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320002"
---
# <a name="ltparamgt"></a>&lt;param&gt;

\<param> 標記應該在方法宣告的註解中用來描述參數的其中一個方法。

## <a name="syntax"></a>語法

```
<param name='name'>description</param>
```

#### <a name="parameters"></a>參數

*name*<br/>
方法參數的名稱。  以單引號或雙引號將名稱括起來。  如果編譯器找不到 `name`，它會發出警告。

*description*<br/>
參數的描述。

## <a name="remarks"></a>備註

\<param> 標記的文字將會顯示於 IntelliSense、[物件瀏覽器](/visualstudio/ide/viewing-the-structure-of-code)以及程式碼結構 Web 報告中。

編譯搭配 [/doc](doc-process-documentation-comments-c-cpp.md) 可處理檔案的文件註解。

## <a name="example"></a>範例

```cpp
// xml_param_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_param_tag.dll
/// Text for class MyClass.
public ref class MyClass {
   /// <param name="Int1">Used to indicate status.</param>
   void MyMethod(int Int1) {
   }
};
```

## <a name="see-also"></a>另請參閱

[XML 文件](xml-documentation-visual-cpp.md)
