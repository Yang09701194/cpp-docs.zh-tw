---
title: "從 [屬性] 視窗中取得欄位描述 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "屬性視窗, 欄位描述"
ms.assetid: 7d92bb6a-b9b9-4cd8-99e9-b5ee129b52a3
caps.latest.revision: 9
caps.handback.revision: 9
manager: "douge"
---
# 從 [屬性] 視窗中取得欄位描述
在 \[屬性\] 視窗底部的描述區域會顯示選取的屬性欄位相關資訊。 這項功能預設為開啟。 如果想要隱藏描述欄位，請以滑鼠右鍵按一下 \[屬性\] 視窗，然後按一下 \[描述\]。 這樣也會移除功能表視窗之 \[描述\] 標題旁的核取記號。 只要依照相同的步驟切換 \[描述\]，就可以再次顯示欄位。  
  
 描述欄位中的資訊出自 <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo>。 每個方法、介面、coclass 等在類型程式庫中都可以有未當地語系化的 `helpstring` 屬性。 \[屬性\] 視窗從 <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo.GetDocumentation%2A> 擷取字串。  
  
### 指定當地語系化的說明字串  
  
1.  請將 `helpstringdll` 屬性加入類型程式庫 \(`typelib`\) 的 library 陳述式。  
  
    > [!NOTE]
    >  如果類型程式庫位於物件程式庫 \(.olb\) 檔案中，這個步驟就是選擇性的。  
  
2.  為字串指定 `helpstringcontext` 屬性。 您也可以指定 `helpstring` 屬性。  
  
     這些屬性與 `helpfile` 和 `helpcontext` 屬性不同，它們位在說明主題的實際 .chm 檔案中。  
  
 若要擷取描述資訊以顯示反白的屬性名稱，\[屬性\] 視窗會為已選取的屬性呼叫 <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetDocumentation2%2A>，指定想要的輸出字串 `lcid` 屬性。 對內，<xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2> 會尋找 `helpstringdll` 屬性中指定的 .dll 檔案，並以指定的內容和 `lcid` 屬性呼叫 .dll 檔案的 `DLLGetDocumentation`。  
  
 `DLLGetDocumentation` 的特徵標記和實作是：  
  
```  
STDAPI DLLGetDocumentation  
(  
   ITypeLib * /* ptlib */,  
   ITypeInfo * /* ptinfo */,  
   LCID /* lcid */,  
   DWORD dwCtx,  
   BSTR * pbstrHelpString  
);  
```  
  
 `DLLGetDocumentation` 函式必須是 .def 檔案中為 DLL 定義的匯出。  
  
 對內建立的 .olb 檔案，其實是個 DLL。 這個 DLL 包含一項資源、類型程式庫 \(.tlb\) 檔案，以及匯出的函式 `DLLGetDocumentation`。  
  
 如果是 .olb 檔案，`helpstringdll` 屬性即是選擇性的，因為它是包含了 .tlb 檔案本身的同一個檔案。  
  
 若要取得在 \[描述\] 窗格中顯示的字串，您至少要在類型程式庫中指定 `helpstring` 屬性。 如果希望當地語系化這些字串，您必須指定 `helpstringdll` \(選擇性\) 屬性和 `helpstringcontext` \(必要\) 屬性並實作 `DLLGetDocumentation`。  
  
 透過 idl 的 `helpstringcontext` 屬性和 `DLLGetDocumentation` 取得當地語系化資訊時，不必實作其他介面。  
  
 取得屬性的當地語系化名稱和說明的另一個方式，是實作 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.GetLocalizedPropertyInfo%2A>。 如需實作這個方法的詳細資訊，請參閱 [屬性視窗中的欄位和介面](../Topic/Properties%20Window%20Fields%20and%20Interfaces.md)。  
  
## 請參閱  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>   
 [屬性視窗中的欄位和介面](../Topic/Properties%20Window%20Fields%20and%20Interfaces.md)   
 [擴充屬性](../Topic/Extending%20Properties.md)   
 [helpstringdll](../windows/helpstringdll.md)   
 [helpstring](../windows/helpstring.md)   
 [helpstringcontext](../windows/helpstringcontext.md)   
 [helpcontext](../windows/helpcontext.md)   
 [helpfile](../windows/helpfile.md)   
 [lcid](../windows/lcid.md)