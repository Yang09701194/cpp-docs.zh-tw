---
title: 如何： 使用 C# 索引子 (C + + /CLI) |Microsoft 文件
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++, indexers
- indexers, consuming C#
ms.assetid: 5a11850c-a1a2-4a0a-b95e-f6dc5a87f439
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 00a8164b91a4e483330d4969325a7bd4b6fe6e6a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-consume-a-c-indexer-ccli"></a>如何：使用 C# 索引子 (C++/CLI)
Visual c + + 不包含索引子。它具有索引的屬性。 若要使用 C# 索引子，存取索引子，就好像索引的屬性。  
  
 如需索引子的詳細資訊，請參閱：  
  
-   [索引子](/dotnet/csharp/programming-guide/indexers/index)  
  
## <a name="example"></a>範例  
 下列 C# 程式會定義索引子。  
  
```  
// consume_cs_indexers.cs  
// compile with: /target:library  
using System;  
public class IndexerClass {  
   private int [] myArray = new int[100];   
   public int this [int index] {   // Indexer declaration  
      get {  
         // Check the index limits.  
         if (index < 0 || index >= 100)  
            return 0;  
         else  
            return myArray[index];  
      }  
      set {  
         if (!(index < 0 || index >= 100))  
            myArray[index] = value;  
      }  
   }  
}  
/*  
// code to consume the indexer  
public class MainClass {  
   public static void Main() {  
      IndexerClass b = new IndexerClass();  
  
      // Call indexer to initialize elements 3 and 5  
      b[3] = 256;  
      b[5] = 1024;  
      for (int i = 0 ; i <= 10 ; i++)   
         Console.WriteLine("Element #{0} = {1}", i, b[i]);  
   }  
}  
*/  
```  
  
## <a name="example"></a>範例  
 此 Visual c + + 程式中，會使用索引子。  
  
```  
// consume_cs_indexers_2.cpp  
// compile with: /clr  
#using "consume_cs_indexers.dll"  
using namespace System;  
  
int main() {  
   IndexerClass ^ ic = gcnew IndexerClass;  
   ic->default[0] = 21;  
   for (int i = 0 ; i <= 10 ; i++)  
      Console::WriteLine("Element #{0} = {1}", i, ic->default[i]);  
}  
```  
  
```Output  
Element #0 = 21  
Element #1 = 0  
Element #2 = 0  
Element #3 = 0  
Element #4 = 0  
Element #5 = 0  
Element #6 = 0  
Element #7 = 0  
Element #8 = 0  
Element #9 = 0  
Element #10 = 0  
```  
  
## <a name="see-also"></a>另請參閱  
 [與其他 .NET 語言間的互通性 (C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)