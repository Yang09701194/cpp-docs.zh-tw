---
title: "編輯後繼續的錯誤和警告 (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.csharp.enc.error_4001"
  - "vs.csharp.enc.error_4034"
  - "vs.csharp.enc.error_4003"
  - "vs.csharp.enc.error_4026"
  - "vs.csharp.enc.error_4032"
  - "vs.csharp.enc.error_4017"
  - "vs.csharp.enc.error_4053"
  - "vs.csharp.enc.error_4024"
  - "vs.csharp.enc.error_4012"
  - "vs.csharp.enc.error_4066"
  - "vs.csharp.enc.error_4020"
  - "vs.csharp.enc.error_4008"
  - "vs.csharp.enc.error_4033"
  - "vs.csharp.enc.error_4014"
  - "vs.csharp.enc.error_4023"
  - "vs.csharp.enc.error_4011"
  - "vs.csharp.enc.error_4006"
  - "vs.csharp.enc.error_4059"
  - "vs.csharp.enc.error_4015"
  - "vs.csharp.enc.error_4018"
  - "vs.csharp.enc.error_4028"
  - "vs.csharp.enc.error_4013"
  - "vs.csharp.enc.error_4009"
  - "vs.csharp.enc.error_4021"
  - "vs.csharp.enc.error_4065"
  - "vs.csharp.enc.error_4029"
  - "vs.csharp.enc.error_4058"
  - "vs.csharp.enc.error_4019"
  - "vs.csharp.enc.error_4007"
  - "vs.csharp.enc.error_4052"
  - "vs.csharp.enc.error_4025"
  - "vs.csharp.enc.error_4055"
  - "vs.csharp.enc.error_4022"
  - "vs.csharp.enc.error_4002"
  - "vs.csharp.enc.error_4016"
  - "vs.csharp.enc.error_4043"
  - "vs.csharp.enc.error_4027"
  - "vs.csharp.enc.error_4054"
  - "vs.csharp.enc.error_4004"
  - "vs.csharp.enc.error_4010"
  - "vs.csharp.enc.error_4030"
  - "vs.csharp.enc.error_4005"
  - "vs.csharp.enc.error_4035"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "編輯後繼續 [C#], 錯誤和警告"
  - "錯誤 [C#], 偵錯"
  - "錯誤 [偵錯工具], 編輯後繼續"
ms.assetid: c0e12b0a-8009-4a4a-979f-c804a91a5d9b
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "susanno"
manager: "douge"
---
# 編輯後繼續的錯誤和警告 (C#)
您對程式碼中某個區段進行的編輯，是 Visual C\# \[編輯後繼續\] 不允許的編輯動作。  
  
 [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)] \[編輯後繼續\] 可讓您在中斷模式停止程式執行、變更執行中的程式碼，然後以新加入的變更繼續執行程式。  
  
 通常會禁止影響類別之公用結構的宣告式程式碼編輯，而且不允許對類別內的方法、屬性主體或私用宣告進行某些編輯。 \[編輯後繼續\] 會盡可能將無法編輯的程式碼標示為淺灰色，並顯示錯誤訊息。  
  
 如需 [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)] 的 \[編輯後繼續\] 中支援之編輯的詳細資訊，請參閱[支援的程式碼變更 \(C\#\)](../Topic/Supported%20Code%20Changes%20\(C%23\).md)。 如需特定錯誤或警告的詳細資訊，您可以在 MSDN [Visual C\# IDE 論壇](http://go.microsoft.com/fwlink/?LinkId=214693)上搜尋或張貼。  
  
### 更正這個錯誤  
  
1.  從 \[**偵錯**\] 功能表上選擇 \[**復原**\]，復原變更。  
  
     \-或\-  
  
2.  停止偵錯工作階段，進行編輯，然後開始新的偵錯工作階段。  
  
## 請參閱  
 [編輯後繼續 \(Visual C\#\)](../Topic/Edit%20and%20Continue%20\(Visual%20C%23\).md)