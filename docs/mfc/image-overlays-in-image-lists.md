---
title: Image Overlays in Image Lists | Microsoft Docs
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
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
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
ms.openlocfilehash: 66d21c2435dbab938324bb9bf65fbdf6d5534b5a
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="image-overlays-in-image-lists"></a>Image Overlays in Image Lists
Every image list ([CImageList](../mfc/reference/cimagelist-class.md)) includes a list of images to use as overlay masks. An "overlay mask" is an image drawn transparently over another image. Any image can be used as an overlay mask. You can specify up to four overlay masks per image list.  
  
 You add the index of an image to the list of overlay masks by using the [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) member function, the index of an image, and the index of an overlay mask. Note that the indices for the overlay masks are one-based rather than zero-based.  
  
 You draw an overlay mask over an image using a single call to **Draw**. The parameters include the index of the image to draw and the index of an overlay mask. You must use the [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) macro to specify the index of the overlay mask. You can also specify an overlay image when calling the [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) member function.  
  
## <a name="see-also"></a>See Also  
 [Using CImageList](../mfc/using-cimagelist.md)   
 [Controls](../mfc/controls-mfc.md)


