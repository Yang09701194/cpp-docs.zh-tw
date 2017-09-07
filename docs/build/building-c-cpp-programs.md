---
title: Building C/C++ Programs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vcbuilding
- buildingaprogramVC
dev_langs:
- C++
helpviewer_keywords:
- builds [C++]
- Visual C++ projects, building
- projects [C++], building
- builds [C++], options
- Visual C++, build options
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
caps.latest.revision: 15
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
ms.translationtype: HT
ms.sourcegitcommit: a43e0425c129cf99ed2374845a4350017bebb188
ms.openlocfilehash: 05e5b8707d968707f12c1a9b19c511adaa99ddd2
ms.contentlocale: zh-tw
ms.lasthandoff: 08/30/2017

---
# <a name="building-cc-programs"></a>Building C/C++ Programs

You can build Visual C++ projects either in Visual Studio or on the command line. The Visual Studio IDE uses [MSBuild](../build/msbuild-visual-cpp.md) to build projects and solutions. On the command line, you can use the C/C++ compiler (cl.exe) and linker (link.exe) to build simple projects. To build more complex projects on the command line, you can use MSBuild or [NMAKE](../build/nmake-reference.md). For an overview about how to use [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] to build projects and solutions, see [Compiling and Building](/visualstudio/ide/compiling-and-building-in-visual-studio).  
  
## <a name="in-this-section"></a>In This Section  

[Building C++ Projects in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)  
Discusses how to use the Visual Studio IDE to build your C/C++ project.  
  
[Build C/C++ code on the command line](../build/building-on-the-command-line.md)  
Discusses how to use the C/C++ command-line compiler and build tools that are included in Visual Studio.  
  
[Building C/C++ Isolated Applications and Side-by-side Assemblies](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
Describes the deployment model for Windows Desktop applications, based on the idea of isolated applications and side-by-side assemblies.  
  
[C/C++ Building Reference](../build/reference/c-cpp-building-reference.md)  
Provides links to reference articles about program building in C++, compiler and linker options, and various build tools.  
  
[Configure Visual C++ for 64-bit, x64 targets](../build/configuring-programs-for-64-bit-visual-cpp.md)  
Describes how to configure both Visual Studio and the command line to use the 64-bit toolset and how to target 64-bit architectures, and discusses common migration issues when code is moved to 64-bit architectures.  
  
[Configure Visual C++ for ARM processors](../build/configuring-programs-for-arm-processors-visual-cpp.md)  
Describes the conventions used by ARM processors, and discusses common migration issues when code is moved to ARM architectures.  
  
[Configuring Programs for Windows XP](../build/configuring-programs-for-windows-xp.md)  
Describes how to set the Platform Toolset to target Windows XP development.  
  
## <a name="related-sections"></a>Related Sections  
 [Compiling and Building](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 Describes the Visual Studio build system and tools.
