---
title: Linker Tools Error LNK1120 | Microsoft Docs
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1120
dev_langs:
- C++
helpviewer_keywords:
- LNK1120
ms.assetid: 56aa7d36-921f-4daf-b44d-cca0d4fb1b51
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: MT
ms.sourcegitcommit: 22000a296568c01082c9aef5ceaac8f266bcad5c
ms.openlocfilehash: f183981b9c3bccdf2629e8f5f3bd2c1b07b52b6a
ms.contentlocale: zh-tw
ms.lasthandoff: 09/08/2017

---
# <a name="linker-tools-error-lnk1120"></a>Linker Tools Error LNK1120
*number* unresolved externals  
  
Error LNK1120 reports the count (*number*) of unresolved external symbol errors for this link operation. Most unresolved external symbol errors are reported individually by [Linker Tools Error LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md) and  [Linker Tools Error LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md), which precede this error message, once for each unresolved external symbol error.  
  
To fix this error, correct all of the other unresolved external errors or other linker errors that precede it in the build output. This error is not reported when no unresolved external errors remain.  

