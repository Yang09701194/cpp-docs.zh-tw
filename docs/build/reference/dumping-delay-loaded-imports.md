---
title: 傾印延遲載入的匯入
ms.date: 11/04/2016
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
ms.openlocfilehash: 368c6b851340dd2a39df9a758f15d52ff5104479
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271862"
---
# <a name="dumping-delay-loaded-imports"></a>傾印延遲載入的匯入

可傾印延遲載入匯入使用[dumpbin /imports](imports-dumpbin.md) ，而且顯示的稍有不同的資訊比標準匯入。 它們會隔離到它們自己的傾印 /imports 的區段，並明確地標示為 延遲載入匯入。 如果卸載影像中的資訊時，所會註明。 如果沒有出現的繫結資訊，目標 DLL 的日期/時間戳記會註明，以及匯入的繫結位址。

## <a name="see-also"></a>另請參閱

[延遲載入 DLL 的連結器支援](linker-support-for-delay-loaded-dlls.md)
