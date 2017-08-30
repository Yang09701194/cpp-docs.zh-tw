---
title: 'Walkthrough: Compiling a C++/CLI Program on the Command Line | Microsoft Docs'
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
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
caps.latest.revision: 11
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
ms.openlocfilehash: 44d67c8e7f83ca5433436cf6b851e3f066a930ad
ms.contentlocale: zh-tw
ms.lasthandoff: 08/30/2017

---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>Walkthrough: Compiling a C++/CLI Program on the Command Line
You can create Visual C++ programs that target the Common Language Runtime (CLR) and use the .NET Framework, and build them on the command line. Visual C++ supports the C++/CLI programming language, which has additional types and operators to target the .NET programming model. For an introduction to the C++/CLI language, see [Pure C++: Hello, C++/CLI](http://msdn.microsoft.com/magazine/cc163681.aspx). For general information, see [.NET Programming with C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
 In this walkthrough, you use a text editor to create a basic C++/CLI program, and then compile it on the command line. (You can use your own C++/CLI program instead of typing the one that's shown, or you can use a C++/CLI code sample from another help article. This technique is useful for building and testing small modules that contain no UI elements.)  
  
> [!NOTE]
>  You can also use the Visual Studio IDE to compile C++/CLI programs. For more information, see [Walkthrough: Compiling a C++ Program that Targets the CLR in Visual Studio](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md).  
  
## <a name="prerequisites"></a>Prerequisites  
 You must understand the fundamentals of the C++ language.  
  
## <a name="compiling-a-ccli-program"></a>Compiling a C++/CLI Program  
 The following steps show how to compile a C++/CLI console application that uses .NET Framework classes.  
  
 To enable compilation for C++/CLI, you must use the [/clr](../build/reference/clr-common-language-runtime-compilation.md) compiler option. The Visual C++ compiler generates an .exe file that contains MSIL code—or mixed MSIL and native code—and links to the required .NET Framework libraries.  
  
#### <a name="to-compile-a-ccli-application-on-the-command-line"></a>To compile a C++/CLI application on the command line  
  
1.  Open a **Developer Command Prompt** window. For specific instructions, see [To open a developer command prompt window](../build/building-on-the-command-line.md#developer_command_prompt).  
  
     Administrator credentials may be required to successfully compile the code, depending on the computer's operating system and configuration. To run the command prompt window as an administrator, right-click to open the shortcut menu for the command prompt and then choose **More**, **Run as administrator**.  
  
2.  At the command prompt, enter **notepad basicclr.cpp**.  
  
     Choose **Yes** when you are prompted to create a file.  
  
3.  In Notepad, enter these lines:  
  
    ```  
    int main()  
    {  
        System::Console::WriteLine("This is a C++/CLI program.");  
    }  
    ```  
  
4.  On the menu bar, choose **File**, **Save**.  
  
     You have created a Visual C++ source file that uses a .NET Framework class (<xref:System.Console>) in the <xref:System> namespace.  
  
5.  At the command prompt, enter **cl /clr basicclr.cpp**. The cl.exe compiler compiles the source code into an .obj file that contains MSIL, and then runs the linker to generate an executable program named basicclr.exe.  
  
6.  To run the basicclr.exe program, at the command prompt, enter **basicclr**.  
  
     The program displays this text and exits:  
  
    ```Output  
    This is a C++/CLI program.  
    ```  
  
## <a name="see-also"></a>See Also  
 [C++ Language Reference](../cpp/cpp-language-reference.md)   
 [Building C/C++ Programs](../build/building-c-cpp-programs.md)   
 [Compiler Options](../build/reference/compiler-options.md)
