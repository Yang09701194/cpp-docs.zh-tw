---
title: local （C++ COM 屬性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: d3710eee748a43a1daa5c07d8b3feb6beb8f64fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214743"
---
# <a name="local-c"></a>local (C++)

在介面標頭中使用時，可讓您使用 MIDL 編譯器做為標頭產生器。 在個別函式中使用時，會指定不會產生任何存根的本機程式。

## <a name="syntax"></a>語法

```cpp
[local]
```

## <a name="remarks"></a>備註

**區域** C++屬性的功能與[本機](/windows/win32/Midl/local)MIDL 屬性相同。

## <a name="example"></a>範例

如需如何使用**本機**的範例，請參閱[call_as](call-as.md) 。

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|**介面**，介面方法|
|**可重複**|否|
|**必要屬性**|None|
|**無效屬性**|`dispinterface`|

如需詳細資訊，請參閱 [屬性內容](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另請參閱

[IDL 屬性](idl-attributes.md)<br/>
[介面屬性](interface-attributes.md)<br/>
[方法屬性](method-attributes.md)<br/>
[call_as](call-as.md)
