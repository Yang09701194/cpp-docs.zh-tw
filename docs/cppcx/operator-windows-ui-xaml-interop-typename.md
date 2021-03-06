---
title: 運算子 Windows::UI::Xaml::Interop::TypeName
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: d35056ca1a4e7f06c9f91fe86998a676a12395f2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337004"
---
# <a name="operator-windowsuixamlinteroptypename"></a>運算子 Windows::UI::Xaml::Interop::TypeName

可以從 `Platform::Type` 轉換為 [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename)。

## <a name="syntax"></a>語法

```cpp
Operator TypeName(Platform::Type^ type);
```

### <a name="return-value"></a>傳回值

指定 [時，則傳回](/uwp/api/windows.ui.xaml.interop.typename) Windows::UI::Xaml::Interop::TypeName `Platform::Type^`。

### <a name="remarks"></a>備註

`TypeName` 是用來表示類型資訊的非語言相關 Windows 執行階段結構。 [Platform::Type](../cppcx/platform-type-class.md) 則是 C++ 專屬，並且無法跨應用程式二進位介面 (ABI) 傳遞。 以下是 `TypeName`其中一種在 [Navigate](/uwp/api/windows.ui.xaml.controls.frame.navigate) 函式內的用法：

```cpp
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>範例

下一個範例顯示如何在 `TypeName` 和 `Type`之間轉換。

```cpp
// Convert from Type to TypeName
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>.NET Framework 同等

.NET Framework 程式會將 `TypeName` 視為 [System.Type](/dotnet/api/system.type)。

### <a name="requirements"></a>需求

## <a name="see-also"></a>另請參閱

[運算子 Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform::Type 類別](../cppcx/platform-type-class.md)
