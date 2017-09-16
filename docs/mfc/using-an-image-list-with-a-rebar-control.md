---
title: Using an Image List with a Rebar Control | Microsoft Docs
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
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
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
ms.translationtype: HT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: f2f705dcbc58eae33688197066e5e59874ddb761
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="using-an-image-list-with-a-rebar-control"></a>Using an Image List with a Rebar Control
Each rebar band can contain, among other things, an image from an associated image list. The following procedure details the necessary steps for displaying an image in a rebar band.  
  
### <a name="to-display-images-in-a-rebar-band"></a>To display images in a rebar band  
  
1.  Attach an image list to your rebar control object by making a call to [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist), passing a pointer to an existing image list.  
  
2.  Modify the **REBARBANDINFO** structure to assign an image to a rebar band:  
  
    -   Set the **fMask** member to **RBBIM_IMAGE**, using the bitwise OR operator to include additional flags as necessary.  
  
    -   Set the `iImage` member to the image list index of the image to be displayed.  
  
3.  Initialize any remaining data members, such as the size, text, and handle of the contained child window, with the necessary information.  
  
4.  Insert the new band (with the image) with a call to [CReBarCtrl::InsertBand](../mfc/reference/crebarctrl-class.md#insertband), passing the **REBARBANDINFO** structure.  
  
 The following example assumes that an existing image list object with two images was attached to the rebar control object (`m_wndReBar`). A new rebar band (defined by `rbi`), containing the first image, is added with a call to `InsertBand`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]  
  
## <a name="see-also"></a>See Also  
 [Using CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Controls](../mfc/controls-mfc.md)


