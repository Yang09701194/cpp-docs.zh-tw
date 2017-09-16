---
title: Using an Image List | Microsoft Docs
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
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
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
ms.openlocfilehash: 28533532f589e58307ca6e5624a3faf758d24e06
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="using-an-image-list"></a>Using an Image List
Typical usage of an image list follows the pattern below:  
  
-   Construct a [CImageList](../mfc/reference/cimagelist-class.md) object and call one of the overloads of its [Create](../mfc/reference/cimagelist-class.md#create) function to create an image list and attach it to the `CImageList` object.  
  
-   If you didn't add images when you created the image list, add images to the image list by calling the [Add](../mfc/reference/cimagelist-class.md#add) or [Read](../mfc/reference/cimagelist-class.md#read) member function.  
  
-   Associate the image list with a control by calling the appropriate member function of that control, or draw images from the image list yourself using the image list's [Draw](../mfc/reference/cimagelist-class.md#draw) member function.  
  
-   Perhaps allow the user to drag an image, using the image list's built-in support for dragging.  
  
> [!NOTE]
>  If the image list was created with the **new** operator, you must destroy the `CImageList` object when you are done with it.  
  
## <a name="see-also"></a>See Also  
 [Using CImageList](../mfc/using-cimagelist.md)   
 [Controls](../mfc/controls-mfc.md)


