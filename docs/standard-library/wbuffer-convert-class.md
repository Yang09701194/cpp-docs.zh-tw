---
title: wbuffer_convert Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- wbuffer/stdext::cvt::wbuffer_convert
dev_langs:
- C++
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 20
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
ms.openlocfilehash: 87c43bde8a5b8b029242aaf7b87d5d8f90bbe6ac
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="wbufferconvert-class"></a>wbuffer_convert Class
Describes a stream buffer that controls the transmission of elements to and from a byte stream buffer.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
 : public std::basic_streambuf<Elem, Traits>
```  
  
#### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`Codecvt`|The [locale](../standard-library/locale-class.md) facet that represents the conversion object.|  
|`Elem`|The wide-character element type.|  
|`Traits`|The traits associated with *Elem*.|  
  
## <a name="remarks"></a>Remarks  
 This template class describes a stream buffer that controls the transmission of elements of type `_Elem`, whose character traits are described by the class `Traits`, to and from a byte stream buffer of type `std::streambuf`.  
  
 Conversion between a sequence of `Elem` values and multibyte sequences is performed by an object of class `Codecvt<Elem, char, std::mbstate_t>`, which meets the requirements of the standard code-conversion facet `std::codecvt<Elem, char, std::mbstate_t>`.  
  
 An object of this template class stores:  
  
-   A pointer to its underlying byte stream buffer  
  
-   A pointer to the allocated conversion object (which is freed when the [wbuffer_convert](../standard-library/wbuffer-convert-class.md)

