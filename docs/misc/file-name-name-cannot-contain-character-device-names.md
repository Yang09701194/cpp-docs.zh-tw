---
title: "File name &lt;name&gt; cannot contain character device names. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.0x800A0077"
  - "vs.message.VB_E_TERRFILECHARDEVINVALID"
ms.assetid: bb6e2e7a-1387-49be-927e-1dbbcafb65b1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# File name &lt;name&gt; cannot contain character device names.
當輸入的檔名實際上是磁碟機的字母代號時，一般會發生此錯誤。  磁碟機的字母代號包含 CON、PRN、AUX、CLOCK$、NUL、LPT1、LPT2、COM1、COM2、COM3 和 COM4，但不受限於只有這些。  
  
### 若要更正這個錯誤  
  
1.  請輸入不同的檔名。  
  
## 請參閱  
 [NIB: Save File As Dialog Box](http://msdn.microsoft.com/zh-tw/22380a20-2858-4391-b2f2-80c6bce64f14)   
 [專案和方案](../Topic/Solutions%20and%20Projects%20in%20Visual%20Studio.md)