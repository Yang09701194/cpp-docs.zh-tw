---
title: "處理文件中的命令 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8d27698d573e1dee539f93ab88015285648fa77
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="handling-commands-in-the-document"></a>處理文件中的命令
文件類別可能也會處理功能表項目、 工具列按鈕或快速鍵產生的特定命令。 根據預設， **CDocument**處理儲存和另存新檔 命令在 檔案 功能表上使用的序列化。 其他會影響資料的命令也可由您的文件的成員函式處理。 例如，在 Scribble 程式中，類別`CScribDoc`編輯全部清除 命令，這會刪除所有目前儲存在文件中的資料提供的處理常式。 文件可以有訊息對應，但不同檢視，於文件無法處理標準 Windows 訊息 — 僅**WM_COMMAND**訊息或"命令 >。  
  
## <a name="see-also"></a>請參閱  
 [使用文件](../mfc/using-documents.md)
