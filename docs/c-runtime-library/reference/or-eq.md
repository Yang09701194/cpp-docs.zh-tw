---
title: or_eq | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- std::or_eq
- or_eq
- std.or_eq
dev_langs:
- C++
helpviewer_keywords:
- or_eq function
ms.assetid: 1eb92464-ed58-40d8-a30e-f0a6aa2f4318
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9ecaefb43dfea22be2a0bdeb34a3de2e476b356
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398620"
---
# <a name="oreq"></a>or_eq

&#124;= 運算子的替代項目。

## <a name="syntax"></a>語法

```C

#define or_eq |=

```

## <a name="remarks"></a>備註

巨集會產生 &#124;= 運算子。

## <a name="example"></a>範例

```cpp
// iso646_oreq.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 3, b = 2, result;

   result= a |= b;
   cout << result << endl;

   result= a or_eq b;
   cout << result << endl;
}
```

```Output
3
3
```

## <a name="requirements"></a>需求

**標頭：**\<iso646.h>