---
title: '&lt;許可權 > （C++檔批註）'
ms.date: 11/04/2016
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
ms.openlocfilehash: e7f0a59c85e3fa28d24e44953e207151c3afa0f4
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988674"
---
# <a name="ltpermissiongt"></a>&lt;permission&gt;

\<permission> 標記可讓您記載成員存取權。 <xref:System.Security.PermissionSet> 可讓您指定成員存取權。

## <a name="syntax"></a>語法

```
<permission cref="member">description</permission>
```

#### <a name="parameters"></a>參數

*成員*<br/>
可從目前編譯環境呼叫的成員或欄位參考。 編譯器會檢查指定的程式碼項目是否存在，並將 `member` 轉譯為輸出 XML 中的標準項目名稱。  以單引號或雙引號將名稱括起來。

如果編譯器找不到 `member`，它會發出警告。

如需如何建立泛型型別 cref 參考的資訊，請參閱[\<see>](see-visual-cpp.md)。

*description*<br/>
成員存取權的描述。

## <a name="remarks"></a>備註

使用 [/doc](doc-process-documentation-comments-c-cpp.md) 編譯，可處理檔案的文件註解。

MSVC 編譯器會嘗試透過檔批註來解析一次中的 cref 參考。  因此，如果使用 C++ 查閱規則，當編譯器找不到符號時，參考就會被標記為無法解析。 如需詳細資訊，請參閱 [\<seealso>](seealso-visual-cpp.md)。

## <a name="example"></a>範例

```cpp
// xml_permission_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_permission_tag.dll
using namespace System;
/// Text for class TestClass.
public ref class TestClass {
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>
   void Test() {}
};
```

## <a name="see-also"></a>請參閱

[XML 文件](xml-documentation-visual-cpp.md)
