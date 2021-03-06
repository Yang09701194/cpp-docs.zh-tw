---
title: _InterlockedAdd 內建函式
ms.date: 09/02/2019
f1_keywords:
- _InterlockedAdd64_acq_cpp
- _InterlockedAdd64_acq
- _InterlockedAdd_acq
- _InterlockedAdd_nf
- _InterlockedAdd64_rel
- _InterlockedAdd64
- _InterlockedAdd_cpp
- _InterlockedAdd_rel_cpp
- _InterlockedAdd_rel
- _InterlockedAdd64_rel_cpp
- _InterlockedAdd64_cpp
- _InterlockedAdd_acq_cpp
- _InterlockedAdd64_nf
- _InterlockedAdd
helpviewer_keywords:
- _InterlockedAdd_nf intrinsic
- _InterlockedAdd_rel intrinsic
- _InterlockedAdd intrinsic
- _InterlockedAdd64 intrinsic
- _InterlockedAdd64_acq intrinsic
- _InterlockedAdd64_nf intrinsic
- _InterlockedAdd_acq intrinsic
- _InterlockedAdd64_rel intrinsic
ms.assetid: 3d319603-ea9c-4fdd-ae61-e52430ccc3b1
ms.openlocfilehash: c540cfe6abd8ae6dc2933e7fb21e2a331c21ea71
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217733"
---
# <a name="_interlockedadd-intrinsic-functions"></a>_InterlockedAdd 內建函式

**Microsoft 專屬**

這些函式會執行不可部分完成的加法, 這可確保當有一個以上的執行緒具有共用變數的存取權時, 作業會順利完成。

## <a name="syntax"></a>語法

```C
long _InterlockedAdd(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_acq(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_nf(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_rel(
   long volatile * Addend,
   long Value
);
__int64 _InterlockedAdd64(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_acq(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_nf (
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_rel(
   __int64 volatile * Addend,
   __int64 Value
);
```

### <a name="parameters"></a>參數

*加數*\
[in、out]要加入至之整數的指標;已由加法的結果取代。

*Value*\
在要加入的值。

## <a name="return-value"></a>傳回值

兩個函式都傳回相加的結果。

## <a name="requirements"></a>需求

|內建|架構|
|---------------|------------------|
|`_InterlockedAdd`|ARM、ARM64|
|`_InterlockedAdd_acq`|ARM、ARM64|
|`_InterlockedAdd_nf`|ARM、ARM64|
|`_InterlockedAdd_rel`|ARM、ARM64|
|`_InterlockedAdd64`|ARM、ARM64|
|`_InterlockedAdd64_acq`|ARM、ARM64|
|`_InterlockedAdd64_nf`|ARM、ARM64|
|`_InterlockedAdd64_rel`|ARM、ARM64|

**標頭檔**\<intrin.h. h >

## <a name="remarks"></a>備註

這些函式的 `_acq` 或 `_rel` 版本後置字元在取得或發行語意之後執行連鎖相加。 *取得語義*表示在任何後續的記憶體讀取和寫入之前, 所有線程和處理器都會看到作業的結果。 在進入關鍵區段時，取得非常有用。 *發行語義*表示所有的記憶體讀取和寫入都強制在作業的結果變成可見之前, 讓所有線程和處理器都可以看見。 離開關鍵區段時，發行非常有用。 具有`_nf` (「無範圍」) 尾碼的內建函式不會做為記憶體屏障。

這些常式僅以內建函式的形式供您使用。

## <a name="example"></a>範例

```cpp
// interlockedadd.cpp
// Compile with: /Oi /EHsc
// processor: ARM
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_InterlockedAdd)

int main()
{
        long data1 = 0xFF00FF00;
        long data2 = 0x00FF0000;
        long retval;
        retval = _InterlockedAdd(&data1, data2);
        printf("0x%x 0x%x 0x%x", data1, data2, retval);
}
```

## <a name="output"></a>Output

```Output
0xffffff00 0xff0000 0xffffff00
```

## <a name="example"></a>範例

```cpp
// interlockedadd64.cpp
// compile with: /Oi /EHsc
// processor: ARM
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_InterlockedAdd64)

int main()
{
        __int64 data1 = 0x0000FF0000000000;
        __int64 data2 = 0x00FF0000FFFFFFFF;
        __int64 retval;
        cout << hex << data1 << " + " << data2 << " = " ;
        retval = _InterlockedAdd64(&data1, data2);
        cout << data1 << endl;
        cout << "Return value: " << retval << endl;
}
```

## <a name="output"></a>Output

```Output
ff0000000000 + ff0000ffffffff = ffff00ffffffff
Return value: ffff00ffffffff
```

**結束 Microsoft 專屬**

## <a name="see-also"></a>另請參閱

[編譯器內建函式](../intrinsics/compiler-intrinsics.md)\
[與 x86 編譯器衝突](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
