---
title: 連結器工具警告 LNK4071 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4071
dev_langs:
- C++
helpviewer_keywords:
- LNK4071
ms.assetid: 803f8c34-8219-4f55-a4ae-7133ceff2ba3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2cb0d4b8d78eb8c7cf1812abb1a7981c605f2c4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4071"></a>連結器工具警告 LNK4071
無法以累加方式連結上後續連結  
  
 找到多個定義的一個或多個符號連結，但[/強制](../../build/reference/force-force-file-output.md)或 **/force: multiple 都會**用來建立輸出檔案，無論錯誤。 刪除累加狀態 (.ilk) 檔案的連結。