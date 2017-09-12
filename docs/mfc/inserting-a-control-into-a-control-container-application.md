---
title: 'ActiveX Control Containers: Inserting a Control into a Control Container Application | Microsoft Docs'
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
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
caps.latest.revision: 9
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
ms.openlocfilehash: 5a457d9a357e488795d9f06dbaff56d5ff5f59e4
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>ActiveX Control Containers: Inserting a Control into a Control Container Application
Before you can access an ActiveX control from an ActiveX control container application, you must add the ActiveX control to the container application using the [Insert ActiveX Control](../windows/insert-activex-control-dialog-box.md) dialog box.  
  
 To add an ActiveX control to the ActiveX control container project, see [Viewing and Adding ActiveX Controls to a Dialog Box](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Once you add the control, you need to add a member variable (of the ActiveX control type) to the dialog box class. For more information on this procedure, see [Adding a Member Variable](../ide/adding-a-member-variable-visual-cpp.md).  
  
 Once you have added the member variable a class, referred to as a wrapper class, is automatically generated and added to your project. This class is used as an interface between the control container and the embedded control.  
  
## <a name="see-also"></a>See Also  
 [ActiveX Control Containers](../mfc/activex-control-containers.md)


