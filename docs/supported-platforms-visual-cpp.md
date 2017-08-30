---
title: Supported Platforms (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
caps.latest.revision: 22
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
ms.sourcegitcommit: a43e0425c129cf99ed2374845a4350017bebb188
ms.openlocfilehash: 78fac089c9b21825bfb014fe6f26776bac58bd93
ms.contentlocale: zh-tw
ms.lasthandoff: 08/30/2017

---
# <a name="supported-platforms-visual-c"></a>Supported Platforms (Visual C++)

Apps built by using [!INCLUDE[vsprvs](assembler/masm/includes/vsprvs_md.md)] can be targeted to various platforms, as follows.  
  
|Operating System|x86|x64|ARM|  
|----------------------|---------|---------|---------|  
|Windows XP|X*|X*||  
|[!INCLUDE[WinXPSvr](build/includes/winxpsvr_md.md)]|X*|X*||  
|Windows Vista|X|X||  
|Windows Server 2008|X|X||  
|Windows 7|X|X||  
|Windows Server 2012 R2|X|X||  
|Windows 8|X|X|X|  
|Windows 8.1|X|X|X|  
|Windows 10|X|X|X|  
|Android **|X|X|X|  
|iOS **|X|X|X|  
|Linux ***|X|X|X|  
  
\* You can use the Windows XP platform toolset included in Visual Studio 2017, Visual Studio 2015, Visual Studio 2013, and Visual Studio 2012 Update 1 or later to build Windows XP and [!INCLUDE[WinXPSvr](build/includes/winxpsvr_md.md)] projects. For information on how to use this platform toolset, see [Configuring Programs for Windows XP](build/configuring-programs-for-windows-xp.md). For additional information on changing the platform toolset, see [How to: Modify the Target Framework and Platform Toolset](build/how-to-modify-the-target-framework-and-platform-toolset.md).  
  
\*\* You can install the **Mobile development with C++** workload in the Visual Studio installer (or the optional **Visual C++ for Cross Platform Mobile Development** component in Visual Studio 2015 setup) to target iOS or Android platforms. For instructions, see [Install Visual C++ for Cross-Platform Mobile Development](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development). To build iOS code, you must have a Mac computer and meet other requirements. For a list of prerequisites and installation instructions, see [Install And Configure Tools to Build using iOS](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios). You can build x86 or ARM code to match the target hardware. Use x86 configurations to build for the iOS simulator, Microsoft Visual Studio Emulator for Android, and some Android devices. Use ARM configurations to build for iOS devices and most Android devices.  
  
\*\*\* You can install the **Linux development with C++** workload in the Visual Studio installer to target Linux platforms. For instructions, see [Download, Install and Setup the Linux Workload](linux/download-install-and-setup-the-linux-development-workload.md). This toolset compiles your executable on the target machine, so you can build for any supported architecture.  

For information about how to set the target platform configuration, see [How to: Configure Visual C++ Projects to Target 64-Bit, x64 Platforms](build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).  
  
## <a name="see-also"></a>See Also  

[Visual C++ Tools and Features in Visual Studio Editions](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)   
[Getting Started](/visualstudio/ide/getting-started-with-visual-cpp-in-visual-studio)
