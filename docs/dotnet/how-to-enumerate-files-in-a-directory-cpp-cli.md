---
title: "如何：列舉目錄中的檔案 (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "目錄 [C++], 列出檔案"
  - "檔案 [C++], 列出檔案"
ms.assetid: ebfc2666-229f-4b94-a9a1-e8f1b5d946d6
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 如何：列舉目錄中的檔案 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

下列程式碼範例會示範如何擷取目錄中檔案的清單。  此外也會列舉子目錄。  下列程式碼範例會使用 <xref:System.IO.Directory.GetFiles%2A>、<xref:System.IO.Directory.GetFiles%2A> 和 <xref:System.IO.Directory.GetDirectories%2A> 方法，顯示 C:\\Windows 目錄的內容。  
  
## 範例  
  
```  
// enum_files.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ folder = "C:\\";  
   array<String^>^ dir = Directory::GetDirectories( folder );  
   Console::WriteLine("--== Directories inside '{0}' ==--", folder);  
   for (int i=0; i<dir->Length; i++)  
      Console::WriteLine(dir[i]);  
  
   array<String^>^ file = Directory::GetFiles( folder );  
   Console::WriteLine("--== Files inside '{0}' ==--", folder);  
   for (int i=0; i<file->Length; i++)  
      Console::WriteLine(file[i]);  
  
   return 0;  
}  
```  
  
## 請參閱  
 [檔案和資料流 I\/O](../Topic/File%20and%20Stream%20I-O.md)   
 [以 C\+\+\/CLI 進行 .NET 程式設計](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)