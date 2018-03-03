---
title: "即時線上關鍵字 （c + + 元件擴充功能） |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- internal_CPP
dev_langs:
- C++
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1d5af53c04c6ff9ec28e7b83cd3a8f9bce8307c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="context-sensitive-keywords--c-component-extensions"></a>視內容而有所區別的關鍵字 (C++ 元件擴充功能)
*即時線上關鍵字*是只在特定內容中才能辨識的語言項目。 在特定內容之外，內容相關性關鍵字可以是使用者定義的符號。  
  
## <a name="all-runtimes"></a>所有執行階段  
 **備註**  
  
 下列是內容相關性關鍵字清單：  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [event](../windows/event-cpp-component-extensions.md)  
  
-   [finally](../dotnet/finally.md)  
  
-   [for each, in](../dotnet/for-each-in.md)  
  
-   [initonly](../dotnet/initonly-cpp-cli.md)  
  
-   `internal`   
  
-   [常值](../windows/literal-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [屬性](../windows/property-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   `where`(屬於[泛型](../windows/generics-cpp-component-extensions.md))  
  
 基於可讀性目的，您可能想要限制內容相關性關鍵字做為使用者定義符號的使用。  
  
## <a name="windows-runtime"></a>Windows 執行階段  
 **備註**  
  
 (沒有這項功能的平台特定備註。)  
  
### <a name="requirements"></a>需求  
 編譯器選項： **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **備註**  
  
 (沒有這項功能的平台特定備註。)  
  
### <a name="requirements"></a>需求  
 編譯器選項： **/clr**  
  
### <a name="examples"></a>範例  
 **範例**  
  
 下列程式碼範例會示範，在適當的內容中，`property` 內容相關性關鍵字可用來定義屬性和變數。  
  
```  
// context_sensitive_keywords.cpp  
// compile with: /clr  
public ref class C {  
   int MyInt;  
public:  
   C() : MyInt(99) {}  
  
   property int Property_Block {   // context-sensitive keyword  
      int get() { return MyInt; }  
   }  
};  
  
int main() {  
   int property = 0;               // variable name  
   C ^ MyC = gcnew C();  
   property = MyC->Property_Block;  
   System::Console::WriteLine(++property);  
}  
```  
  
 **輸出**  
  
```Output  
100  
```  
  
## <a name="see-also"></a>請參閱  
 [執行階段平台的元件延伸模組](../windows/component-extensions-for-runtime-platforms.md)