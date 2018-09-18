---
title: 連結器工具警告 LNK4010 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4010
dev_langs:
- C++
helpviewer_keywords:
- LNK4010
ms.assetid: 2824cf99-4174-4b60-a6e2-c01e9f1ee52d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e214f603c31c72533d81a140023363880532191c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068063"
---
# <a name="linker-tools-warning-lnk4010"></a>連結器工具警告 LNK4010

無效的子系統版本號碼數字，假設預設的子系統版本

您可以指定映像的子系統版本 ([/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md))。 每個子系統有最低版本需求。 如果指定的版本低於最小值，會發生這個警告，並連結器就會直接使用預設的子系統。