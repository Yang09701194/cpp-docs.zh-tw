---
title: -Wp64 (Detect 64-Bit Portability Issues) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
dev_langs:
- C++
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
caps.latest.revision: 21
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: a43e0425c129cf99ed2374845a4350017bebb188
ms.openlocfilehash: 06f035f2208558f99e50833c576896a2088f5ed6
ms.contentlocale: zh-tw
ms.lasthandoff: 08/30/2017

---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (Detect 64-Bit Portability Issues)

This compiler option is obsolete. In versions of Visual Studio before Visual Studio 2013, this detects 64-bit portability problems on types that are also marked with the [__w64](../../cpp/w64.md) keyword.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Wp64  
```  
  
## <a name="remarks"></a>Remarks  

By default, in versions of Visual Studio before Visual Studio 2013, the **/Wp64** compiler option is off in the Visual C++ compiler that builds 32-bit x86 code, and on in the Visual C++ compiler that builds 64-bit, x64 code.  
  
> [!IMPORTANT]
>  The [/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md) compiler option and [__w64](../../cpp/w64.md) keyword are deprecated in Visual Studio 2010 and Visual Studio 2012, and not supported starting in Visual Studio 2013. If you convert a project that uses this switch, the switch will not be migrated during conversion. To use this option in Visual Studio 2010 or Visual Studio 2012, you must type the compiler switch under **Additional Options** in the **Command Line** section of the project properties. If you use the **/Wp64** compiler option on the command line, the compiler issues Command-Line Warning D9002. Instead of using this option and keyword to detect 64-bit portability issues, use a Visual C++ compiler that targets a 64-bit platform and specify the [/W4](../../build/reference/compiler-option-warning-level.md) option. For more information, see [Configure Visual C++ for 64-bit, x64 targets](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
Variables of the following types are tested on a 32-bit operating system as if they were being used on a 64-bit operating system:  
  
-   int  
  
-   long  
  
-   pointer  
  
 If you regularly compile your application by using a compiler that builds 64-bit, x64 code, you can just disable **/Wp64** in your 32-bit compilations because the 64-bit compiler will detect all issues. For more information about how to target a Windows 64-bit operating system, see [Configure Visual C++ for 64-bit, x64 targets](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>To set this compiler option in the Visual Studio development environment  
  
1.  Open the project **Property Pages** dialog box.  
  
     For more information, see [Working with Project Properties](../../ide/working-with-project-properties.md).  
  
2.  Click the **C/C++** folder.  
  
3.  Click the **Command Line** property page.  
  
4.  Modify the **Additional Options** box to include **/Wp64**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>To set this compiler option programmatically  
  
-   See <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.  
  
## <a name="see-also"></a>See Also  

[Compiler Options](../../build/reference/compiler-options.md)   
[Setting Compiler Options](../../build/reference/setting-compiler-options.md)   
[Configure Visual C++ for 64-bit, x64 targets](../../build/configuring-programs-for-64-bit-visual-cpp.md)
