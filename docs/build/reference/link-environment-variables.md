---
title: LINK Environment Variables | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
caps.latest.revision: 8
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
ms.openlocfilehash: f9e816f2f6309af33ed7517616033abf8cd3b82e
ms.contentlocale: zh-tw
ms.lasthandoff: 08/30/2017

---
# <a name="link-environment-variables"></a>LINK Environment Variables

The LINK tool uses the following environment variables:  
  
-   LINK and _LINK\_, if defined. The LINK tool prepends the options and arguments defined in the LINK environment variable and appends the options and arguments defined in the _LINK\_ environment variable to the command line arguments before processing.  
  
-   LIB, if defined. The LINK tools uses the LIB path when searching for an object, library, or other file specified on the command line or by the [/BASE](../../build/reference/base-base-address.md) option. It also uses the LIB path to find a .pdb file named in an object. The LIB variable can contain one or more path specifications, separated by semicolons. One path must point to the \lib subdirectory of your Visual C++ installation.  
  
-   PATH, if the tool needs to run CVTRES and cannot find the file in the same directory as LINK itself. (LINK requires CVTRES to link a .res file.) PATH must point to the \bin subdirectory of your Visual C++ installation.  
  
-   TMP, to specify a directory when linking OMF or .res files.  
  
## <a name="see-also"></a>See Also  

[Setting Linker Options](../../build/reference/setting-linker-options.md)   
[Linker Options](../../build/reference/linker-options.md)   
[Build C/C++ code on the command line](../../build/building-on-the-command-line.md)  
[Set the Path and Environment Variables for Command-Line Builds](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
