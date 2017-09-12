---
title: Image Information in Image Lists | Microsoft Docs
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
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
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
ms.openlocfilehash: d6cd8df43d56af2aed19f8a1e583cb356ad6dfee
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="image-information-in-image-lists"></a>Image Information in Image Lists
[CImageList](../mfc/reference/cimagelist-class.md) includes a number of functions that retrieve information from an image list. The [GetImageInfo](../mfc/reference/cimagelist-class.md#getimageinfo) member function fills an `IMAGEINFO` structure with information about a single image, including the handles of the image and mask bitmaps, the number of color planes and bits per pixel, and the bounding rectangle of the image within the image bitmap. You can use this information to directly manipulate the bitmaps for the image.  
  
 The [GetImageCount](../mfc/reference/cimagelist-class.md#getimagecount) member function retrieves the number of images in an image list.  
  
 You can create an icon based on an image and mask in an image list by using the [ExtractIcon](../mfc/reference/cimagelist-class.md#extracticon) member function. The function returns the handle of the new icon.  
  
## <a name="see-also"></a>See Also  
 [Using CImageList](../mfc/using-cimagelist.md)   
 [Controls](../mfc/controls-mfc.md)


