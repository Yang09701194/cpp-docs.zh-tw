---
title: 'MFC ActiveX Controls: Returning Error Codes From a Method | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
caps.latest.revision: 10
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
ms.translationtype: HT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: d29c889dcc8bb86b024a4dd78954286d8ed6b33f
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX Controls: Returning Error Codes From a Method
This article describes how to return error codes from an ActiveX control method.  
  
 To indicate that an error has occurred within a method, you should use the [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) member function, which takes an `SCODE` (status code) as a parameter. You can use a predefined `SCODE` or define one of your own.  
  
> [!NOTE]
>  `ThrowError` is meant to be used only as a means of returning an error from within a property's Get or Set function or an automation Method. These are the only times that the appropriate exception handler will be present on the stack.  
  
 Helper functions exist for the most common predefined `SCODE`s, such as [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), and [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
 For a list of predefined `SCODE`s and instructions on defining custom `SCODE`s, see the section [Handling Errors in Your ActiveX Control](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX Controls: Advanced Topics.  
  
 For more information on reporting exceptions in other areas of your code, see [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) and the section [Handling Errors in Your ActiveX Control](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX Controls: Advanced Topics.  
  
## <a name="see-also"></a>See Also  
 [MFC ActiveX Controls](../mfc/mfc-activex-controls.md)


