---
title: "註冊服務 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "服務, 註冊"
ms.assetid: c4ebac40-0374-4dda-948e-06fdda0e9c81
caps.latest.revision: 8
caps.handback.revision: 8
manager: "douge"
---
# 註冊服務
若要支援依需求載入，服務提供者必須向 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 註冊其全域服務。  
  
 在開發期間，將屬性加入封裝的原始程式碼，然後在 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE 中建置封裝，受管理服務提供者即會註冊服務和服務覆寫。 這會在產生的組件上執行 RegPkg.exe 公用程式，並註冊封裝，然後準備進行部署。 如需詳細資訊，請參閱[如何：註冊服務](../misc/how-to-register-a-service.md)。  
  
 未受管理的服務提供者必須在系統登錄的 \[services\] 區段或 \[service overrides\] 區段中，向 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 註冊它們所提供的服務。 下列 .reg 檔案片段顯示可能會如何登錄 SVsTextManager 服務：  
  
```  
[HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\<version number>\Services\{F5E7E71D-1401-11d1-883B-0000F87579D2}] @="{F5E7E720-1401-11d1-883B-0000F87579D2}" "Name"="SVsTextManager"  
```  
  
 在上述範例中，版本號碼是 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 版本 \(如 7.1 或 8.0\)、機碼 {F5E7E71D\-1401\-11d1\-883B\-0000F87579D2} 是 SVsTextManager 服務的服務識別項 \(SID\)，而預設值 {F5E7E720\-1401\-11d1\-883B\-0000F87579D2} 是提供該服務之文字管理員 VSPackage 的封裝 GUID。  
  
## 遠端服務和背景執行緒  
 無法自動從遠端使用您所提供的服務，或背景執行緒無法自動使用您所提供的服務。 若要將它們設為可用，您必須建立並註冊類型程式庫。  
  
 從使用 Visual Studio Library \(VSL\) 的 Unmanaged 程式碼，您可以透過這種方式註冊您的類型程式庫：  
  
```  
#define VSL_REGISTER_TYPE_LIB TRUE #include <VSLPackageDllEntryPoints.cpp>  
```  
  
 從 Managed 程式碼，您可以加入建置後步驟，如下所示：  
  
```  
regasm /tlb MyAssembly.dll  
```  
  
## 請參閱  
 [使用並提供服務](../Topic/Using%20and%20Providing%20Services.md)   
 [服務的基本資訊](../Topic/Service%20Essentials.md)