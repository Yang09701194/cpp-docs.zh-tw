---
title: ABC Structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 44d43c678a34cc375b9a2bb4834905d389713a58
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="abc-structure"></a>ABC Structure
The **ABC** structure contains the width of a character in a TrueType font.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _ABC { /* abc */  
    int abcA;  
    UINT abcB;  
    int abcC;  
} ABC;  
```  
  
#### <a name="parameters"></a>Parameters  
 *abcA*  
 Specifies the A spacing of the character. The A spacing is the distance to add to the current position before drawing the character glyph.  
  
 *abcB*  
 Specifies the B spacing of the character. The B spacing is the width of the drawn portion of the character glyph.  
  
 *abcC*  
 Specifies the C spacing of the character. The C spacing is the distance to add to the current position to provide white space to the right of the character glyph.  
  
## <a name="remarks"></a>Remarks  
 The total width of a character is the summation of the A, B, and C spaces. Either the A or the C space can be negative to indicate underhangs or overhangs.  
  
## <a name="requirements"></a>Requirements  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>See Also  
 [Structures, Styles, Callbacks, and Message Maps](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)



