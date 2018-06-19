---
title: 如何： 擷取.NET Framework 版本 (C + + /CLI) |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .NET Framework, version
- Version property, retrieving .NET Framework version
ms.assetid: fc786fbc-c915-4b15-bcad-0d68cf2c44bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f8bc471cda452bd387478a75dd047631c0359ed1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128767"
---
# <a name="how-to-retrieve-the-net-framework-version-ccli"></a>如何：擷取 .NET Framework 版本 (C++/CLI)
下列程式碼範例示範如何判斷目前已安裝.NET Framework 版本<xref:System.Environment.Version%2A>屬性，這是一個指標到<xref:System.Version>物件，包含版本資訊。  
  
## <a name="example"></a>範例  
  
```  
// dotnet_ver.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   Version^ version = Environment::Version;  
   if (version)  
   {  
      int build = version->Build;  
      int major = version->Major;  
      int minor = version->Minor;  
      int revision = Environment::Version->Revision;  
      Console::Write(".NET Framework version: ");  
      Console::WriteLine("{0}.{1}.{2}.{3}",   
            build, major, minor, revision);  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [Windows 作業 (C + + /CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [以 C++/CLI 進行 .NET 程式設計 (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)