---
title: "說明功能表合併 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- menus [MFC], merging
- merging Help menus [MFC]
- Help [MFC], for active document containers
ms.assetid: 9d615999-79ba-471a-9288-718f0c903d49
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c4d3ae9509edcbe79417bb37d02f4f585b2da653
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="help-menu-merging"></a>說明功能表合併
物件在容器內作用時，功能表合併通訊協定 OLE 文件可讓物件完全控制**協助**功能表。 因此，除非使用者停用該物件，否則容器的說明主題無法使用。 現用文件內含項目結構會在就地功能表合併的規則展開，讓容器和作用中現用文件共用功能表。 新規則只是額外的慣例，內容是關於哪些元件擁有功能表的哪些部分，以及共用功能表如何建構。  
  
 新的慣例很簡單。 在現用的文件**協助**功能表有兩個最上層功能表項目組織方式如下：  
  
 `Help`  
  
 `Container Help >`  
  
 `Object Help    >`  
  
 比方說，當的 Word 部分在作用中的 Office Binder 則**協助**功能表會顯示，如下所示：  
  
 `Help`  
  
 `Binder Help >`  
  
 `Word Help   >`  
  
 兩個功能表項目為串聯功能表，其底下容器和物件特有的任何其他功能表項目皆提供給使用者。 這裡顯示的項目視容器和物件而有所不同。  
  
 為了建構這個已合併**協助**功能表，現用文件內含項目結構會修改標準 OLE 文件程序。 根據 OLE 文件，合併的功能表列可以有六個功能表群組，也就是**檔案**，**編輯**，**容器**， `Object`，**視窗**，**協助**，依此順序。 在每個群組中，可以是零或多個功能表。 群組**檔案**，**容器**，和**視窗**屬於容器和群組**編輯**，**物件、**和**協助**屬於的物件。 當物件要進行功能表合併時，它會建立一個空白的功能表列並且將其傳遞至容器。 容器然後插入其功能表，藉由呼叫**ioleinplaceframe:: Insertmenus**。 物件也會傳遞六個 LONG 值陣列的結構 (**OLEMENUGROUPWIDTHS**)。 在插入功能表之後，容器會標示其每個群組中新增了多少功能表，然後傳回。 接著，物件插入其功能表，並請注意各個容器群組中的功能表計數。 最後，物件會將合併的功能表列和陣列 (包含每個群組中的功能表計數) 傳遞至 OLE，而其會傳回不透明「功能表描述元」控制代碼。 稍後物件會傳遞該控制代碼和合併的功能表列到容器中，透過**ioleinplaceframe:: Setmenu**。 此時，容器會顯示合併的功能表列並且將控制代碼傳遞至 OLE，因此 OLE 可以適當分派功能表訊息。  
  
 在修改過的使用中文件程序中，物件必須先初始化**OLEMENUGROUPWIDTHS**為零，再將它傳遞至容器的項目。 然後，容器執行一般功能表插入，有一個例外狀況： 容器會插入**協助**功能表作為最後一個項目，並將值為 1 中的最後一個 （第六個） 的項目**OLEMENUGROUPWIDTHS**陣列（亦即，寬度 [5]，所屬物件的 Help 群組）。 這**協助**功能表會有一個項目即為子功能表，"**容器說明**> 」 串聯功能表如先前所述。  
  
 物件接著會執行其一般功能表插入程式碼，但插入之前其**協助**功能表上，它會檢查的第六個項目**OLEMENUGROUPWIDTHS**陣列。 如果值為 1，而最後一個功能表的名稱是**協助**（或適當的當地語系化字串），然後將物件插入其**協助**做為容器的子功能表的功能表**協助**功能表。  
  
 然後將物件集的第六個項目**OLEMENUGROUPWIDTHS**為零和第五個項目遞增一。 這會讓 OLE 知道**協助**功能表屬於容器，而且對應至該功能表 （和及其子功能表） 的功能表訊息應路由至容器。 然後，它是容器的責任是轉送`WM_INITMENUPOPUP`， **WM_SELECT**， **WM_COMMAND**，和屬於物件的部分的其他功能表相關訊息**協助**功能表。 這會透過使用`WM_INITMENU`清除旗標，告知使用者是否巡覽至物件的容器**協助**功能表。 容器此時`WM_MENUSELECT`進入或在任何項目**協助**容器沒有自行新增的功能表。 項目，則表示使用者已巡覽至物件功能表，讓容器設定 「 在物件說明功能表中 」 旗標，並使用該旗標的狀態轉送任何`WM_MENUSELECT`， `WM_INITMENUPOPUP`，和**WM_COMMAND**訊息，至少為[物件] 視窗中。 (在結束時，容器清會除旗標，然後自行處理這些相同訊息)。容器應會使用從物件傳回的視窗**ioleinplaceactiveobejct::**函式做為這些訊息的目的地。  
  
 如果物件會偵測到的第六個項目中的零**OLEMENUGROUPWIDTHS**，它就會根據標準 OLE 文件規則繼續。 此程序處理參與容器**協助**以及未合併的功能表。  
  
 當物件呼叫**ioleinplaceframe:: Setmenu**，在顯示合併的功能表列，容器會確認是否前**協助**功能表還包含除了此容器的有其他子功能表插入。 如果如此，容器會保留其**協助**功能表合併的功能表列中。 如果**協助**功能表沒有其他的子功能表，容器將會移除其**協助**功能表合併的功能表列。 此程序處理參與物件**協助**以及未合併的功能表。  
  
 最後，需要反組譯功能表時，物件移除插入**協助**功能表除了移除其他插入的功能表。 當容器移除其功能表時，將會移除其**協助**除了其插入的其他功能表的功能表。  
  
## <a name="see-also"></a>請參閱  
 [主動式文件容器](../mfc/active-document-containers.md)
