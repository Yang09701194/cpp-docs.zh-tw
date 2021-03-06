---
title: CA2CAEX 類別
ms.date: 11/04/2016
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
ms.openlocfilehash: 505c1e369bc5949fea291a2172c16d5e52c75567
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168510"
---
# <a name="ca2caex-class"></a>CA2CAEX 類別

字串轉換宏 CA2CTEX 和 CT2CAEX 以及 typedef CA2CA 會使用這個類別。

> [!IMPORTANT]
> 這個類別及其成員無法在 Windows 執行階段中執行的應用程式中使用。

## <a name="syntax"></a>語法

```cpp
template<int t_nBufferLength = 128>
class CA2CAEX
```

### <a name="parameters"></a>參數

*t_nBufferLength*<br/>
轉譯進程中使用的緩衝區大小。 預設長度為128個位元組。

## <a name="members"></a>成員

### <a name="public-constructors"></a>公用建構函式

|名稱|描述|
|----------|-----------------|
|[CA2CAEX::CA2CAEX](#ca2caex)|建構函式。|
|[CA2CAEX：： ~ CA2CAEX](#dtor)|解構函式。|

### <a name="public-operators"></a>公用運算子

|名稱|描述|
|----------|-----------------|
|[CA2CAEX：： operator LPCSTR](#operator_lpcstr)|轉換運算子。|

### <a name="public-data-members"></a>公用資料成員

|名稱|描述|
|----------|-----------------|
|[CA2CAEX：： m_psz](#m_psz)|儲存來源字串的資料成員。|

## <a name="remarks"></a>備註

除非需要額外的功能，否則請在您自己的程式碼中使用 CA2CTEX、CT2CAEX 或 CA2CA。

這個類別可在迴圈中安全使用，而且不會使堆疊溢位。 根據預設，ATL 轉換類別及巨集將使用目前的執行緒 ANSI 字碼頁，來進行轉換。

下列宏是以這個類別為基礎：

- CA2CTEX

- CT2CAEX

下列 typedef 是以這個類別為基礎：

- CA2CA

如需這些文字轉換宏的討論，請參閱[ATL 和 MFC 字串轉換宏](string-conversion-macros.md)。

## <a name="example"></a>範例

如需使用這些字串轉換宏的範例，請參閱[ATL 和 MFC 字串轉換宏](string-conversion-macros.md)。

## <a name="requirements"></a>需求

**標頭：** atlconv.h。h

## <a name="ca2caexca2caex"></a><a name="ca2caex"></a>CA2CAEX::CA2CAEX

建構函式。

```cpp
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>參數

*psz*<br/>
要轉換的文字字串。

*nCodePage*<br/>
未在此類別中使用。

### <a name="remarks"></a>備註

建立翻譯所需的緩衝區。

## <a name="ca2caexca2caex"></a><a name="dtor"></a>CA2CAEX：： ~ CA2CAEX

解構函式。

```cpp
~CA2CAEX() throw();
```

### <a name="remarks"></a>備註

釋放配置的緩衝區。

## <a name="ca2caexm_psz"></a><a name="m_psz"></a>CA2CAEX：： m_psz

儲存來源字串的資料成員。

```cpp
LPCSTR m_psz;
```

## <a name="ca2caexoperator-lpcstr"></a><a name="operator_lpcstr"></a>CA2CAEX：： operator LPCSTR

轉換運算子。

```cpp
operator LPCSTR() const throw();
```

### <a name="return-value"></a>傳回值

傳回文字字串，類型為 LPCSTR。

## <a name="see-also"></a>另請參閱

[CA2AEX 類別](../../atl/reference/ca2aex-class.md)<br/>
[CA2WEX 類別](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX 類別](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX 類別](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX 類別](../../atl/reference/cw2wex-class.md)<br/>
[類別概觀](../../atl/atl-class-overview.md)
