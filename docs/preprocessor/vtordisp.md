---
title: vtordisp pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
ms.openlocfilehash: 3c676ab2bfee1b6cf3caff3ab456a4f23f2744c3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216488"
---
# <a name="vtordisp-pragma"></a>vtordisp pragma

**C++特殊**

控制隱藏`vtordisp`的結構/損毀位移成員的加入。

## <a name="syntax"></a>語法

> **#pragma vtordisp (** [ **push,** ] *n* **)** \
> **#pragma vtordisp (pop)** \
> **#pragma vtordisp ()** \
> **#pragma vtordisp (** [ **push,** ] { **on**  |  **off** } **)**

### <a name="parameters"></a>參數

**式**\
將目前`vtordisp`的設定推送到內部編譯器堆疊上, 並將新`vtordisp`的設定設為*n*。  如果未指定*n* , 則目前`vtordisp`的設定不變。

**提示**\
移除內部編譯器堆疊中的最上層記錄, 並將`vtordisp`設定還原為已移除的值。

*n*\
指定`vtordisp`設定的新值。 可能的值為0、1或 2, 對應于`/vd0`、 `/vd1`和`/vd2`編譯器選項。 如需詳細資訊, 請參閱[/vd (停用結構置換)](../build/reference/vd-disable-construction-displacements.md)。

**的**\
相當於 `#pragma vtordisp(1)`。

**停止**\
相當於 `#pragma vtordisp(0)`。

## <a name="remarks"></a>備註

**Vtordisp** pragma 只適用于使用虛擬基底的程式碼。 如果衍生類別會覆寫它從虛擬基底類別繼承的虛擬函式，而且如果衍生類別的建構函式或解構函式會使用虛擬基底類別的指標呼叫函式，編譯器可能會在內含虛擬基底的類別中採用額外的隱藏 `vtordisp` 欄位。

**Vtordisp** pragma 會影響後面的類別版面配置。 `/vd0`、和選項`/vd2`會針對完整模組指定相同的行為。 `/vd1` 指定0或**off**會抑制隱藏`vtordisp`的成員。 只有在沒有任何可能的類別的程式`this`和析構函式在指標所指向的物件上呼叫虛擬函式時, 才關閉 vtordisp 功能。

指定1或**on**(預設值) 會啟用所`vtordisp`需的隱藏成員。

指定2可讓所有`vtordisp`虛擬基底的隱藏成員具有虛擬函式。  `#pragma vtordisp(2)`可能需要確保部分結構化物件上的**dynamic_cast**有正確的效能。 如需詳細資訊, 請參閱[編譯器警告 (層級 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)。

`#pragma vtordisp()`, 沒有引數, 會將`vtordisp`設定還原為其初始設定。

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

**結束C++特定**

## <a name="see-also"></a>另請參閱

[Pragma 指示詞和 __pragma 關鍵字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
