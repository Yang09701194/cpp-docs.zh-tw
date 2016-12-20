---
title: "命名空間宣告必須要使用 &#39;xmlns&#39; 開頭 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31187"
  - "vbc31187"
helpviewer_keywords: 
  - "BC31187"
ms.assetid: 64c6a033-7cdc-48a0-bff0-bdd045cb13ad
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 命名空間宣告必須要使用 &#39;xmlns&#39; 開頭
已指定 XML 命名空間，但不含必要的 `xmlns` 識別項。`xmlns` 識別項只能包含小寫字元。  
  
 **錯誤 ID：**BC31187  
  
### 更正這個錯誤  
  
-   當您宣告 XML 命名空間時，請使用 `xmlns` 識別碼。 以下是一個範例：  
  
    ```vb#  
    Imports <xmlns:ns="http://SampleNamespace">  
    ```  
  
## 請參閱  
 [Imports Statement \(XML Namespace\)](../Topic/Imports%20Statement%20\(XML%20Namespace\).md)   
 [XML Literals](../Topic/XML%20Literals%20\(Visual%20Basic\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)