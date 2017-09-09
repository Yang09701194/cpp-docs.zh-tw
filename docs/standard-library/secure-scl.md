---
title: _SECURE_SCL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SECURE_SCL
dev_langs:
- C++
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 2b08c83eddb92ac2df89c4038cd87845a83c3159
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="securescl"></a>_SECURE_SCL
  
Superseded by [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), this macro defines whether [Checked Iterators](../standard-library/checked-iterators.md) are enabled. By default, checked iterators are enabled in Debug builds, and disabled in Retail builds.  
  
> [!IMPORTANT]
> Direct use of the `_SECURE_SCL` macro is deprecated. Instead, use `_ITERATOR_DEBUG_LEVEL` to control checked iterator settings. For more information, see [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Remarks  
  
When checked iterators are enabled, unsafe iterator use causes a runtime error and the program is terminated. To enable checked iterators, set `_ITERATOR_DEBUG_LEVEL` to 1 or 2. This is equivalent to a `_SECURE_SCL` setting of 1, or enabled:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 1  
```  
  
To disable checked iterators, set `_ITERATOR_DEBUG_LEVEL` to 0. This is equivalent to a `_SECURE_SCL` setting of 0, or disabled:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
For information on how to disable warnings about checked iterators, see [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## <a name="see-also"></a>See Also  
[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
[Checked Iterators](../standard-library/checked-iterators.md)   
[Debug Iterator Support](../standard-library/debug-iterator-support.md)   
[Safe Libraries: C++ Standard Library](../standard-library/safe-libraries-cpp-standard-library.md)


