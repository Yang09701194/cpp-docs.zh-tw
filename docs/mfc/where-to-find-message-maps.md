---
title: Where to Find Message Maps | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 405b0b58e4b8a5ff9b27aecc12562d94f6b31506
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="where-to-find-message-maps"></a>Where to Find Message Maps
When you create a new skeleton application with the Application Wizard, the Application Wizard writes a message map for each command-target class it creates for you. This includes your derived application, document, view, and frame-window classes. Some of these message maps already have the entries supplied by the Application Wizard for certain messages and predefined commands, and some are just placeholders for handlers that you will add.  
  
 A class's message map is located in the .CPP file for the class. Working with the basic message maps that the Application Wizard creates, you use the Properties window to add entries for the messages and commands that each class will handle. A typical message map might look like the following after you add some entries:  
  
 [!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]  
  
 The message map consists of a collection of macros. Two macros, [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) and [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map), bracket the message map. Other macros, such as `ON_COMMAND`, fill in the message map's contents.  
  
> [!NOTE]
>  The message-map macros are not followed by semicolons.  
  
 When you use the Add Class wizard to create a new class, it provides a message map for the class. Alternatively, you can create a message map manually using the source code editor.  
  
## <a name="see-also"></a>See Also  
 [How the Framework Searches Message Maps](../mfc/how-the-framework-searches-message-maps.md)


