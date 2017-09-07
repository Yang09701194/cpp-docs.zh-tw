---
title: MFC MBCS DLL Add-on | Microsoft Docs
ms.custom: 
ms.date: 08/20/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MBCS
- MFC
ms.assetid: bebec0ff-e019-42ca-b5df-8c218ac5b54a
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 42abd4adfe10b032849bfec391874cd249793c32
ms.openlocfilehash: f6cf9f0626eb2c25faf473d8177b66368280643e
ms.contentlocale: zh-tw
ms.lasthandoff: 08/31/2017

---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL Add-on
 You need the multibyte DLLs in order to build an MFC project in Visual Studio 2015 that has the **Character Set** property set to **Use Multi-Byte Character Set** or **Not Set**.  

**Visual Studio 2013**: Download the DLL at [Multibyte MFC Library for Visual Studio 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40770).

**Visual Studio 2015**: The DLL is included in the Visual C++ setup components. Visual C++ and MFC are optional install configurations in Visual Studio setup. To make sure that MFC is installed, choose **Custom** in setup, and under **Programming Languages**, make sure that **Visual C++** and **Microsoft Foundation Classes for C++** are selected. If you have already installed Visual Studio, you will be prompted to install Visual C++ and/or MFC when you attempt to create an MFC project.  
  
**Visual Studio 2017**: The DLL is installed with the **Desktop Development with C++** workload when you select **MFC and ATL support** from the **Optional Components** pane.

  
## <a name="see-also"></a>See Also  
 [MFC Library Versions](../mfc/mfc-library-versions.md)


