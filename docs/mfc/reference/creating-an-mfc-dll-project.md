---
title: Creating an MFC DLL Project | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfcdll.project
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
caps.latest.revision: 13
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
ms.openlocfilehash: b133538b16801d844109bd57225c0bc09a237a34
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="creating-an-mfc-dll-project"></a>Creating an MFC DLL Project
An MFC DLL is a binary file that acts as a shared library of functions that can be used simultaneously by multiple applications. The easiest way to create an MFC DLL project is to use the MFC DLL Wizard.  
  
> [!NOTE]
>  The appearance of features in the IDE can depend on your active settings or edition, and might differ from those described in Help. To change your settings, choose **Import and Export Settings** on the **Tools** menu. For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>To create an MFC DLL Project using the MFC DLL Wizard  
  
1.  Follow the instructions in the help topic [Creating a Project with a Visual C++ Application Wizard](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
 **Note** In the **New Project** dialog box, select the `MFC DLL` icon in the Templates pane to open the MFC DLL Wizard.  
  
1.  Define your application settings using the [application settings](../../mfc/reference/application-settings-mfc-dll-wizard.md) page of the [MFC DLL Wizard](../../mfc/reference/mfc-dll-wizard.md).  
  
    > [!NOTE]
    >  Skip this step to keep the wizard default settings.  
  
2.  Click **Finish** to close the wizard and open your new project in **Solution Explorer**.  
  
 Once your project is created, you can view the files created in the Solution Explorer. For more information about the files the wizard creates for your project, see the project-generated file ReadMe.txt. For more information about the file types, see [File Types Created for Visual C++ Projects](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
## <a name="see-also"></a>See Also  
 [Visual C++ Project Types](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)   
 [Adding Functionality with Code Wizards](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Property Pages](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)


