---
title: 編譯器警告 （層級 4） C4718 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4718
dev_langs:
- C++
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a92ab7a32babd181f282c799568e3a9dea436c49
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294030"
---
# <a name="compiler-warning-level-4-c4718"></a>編譯器警告 (層級 4) C4718
'function call': 遞迴呼叫沒有副作用，正在刪除  
  
 函式包含遞迴呼叫，但沒有副作用。 正在刪除對此函式的呼叫。 程式的正確性不受影響，但行為受影響。 因為保留呼叫可能會導致執行階段堆疊溢位的例外狀況，所以刪除該呼叫以排除這個可能性。