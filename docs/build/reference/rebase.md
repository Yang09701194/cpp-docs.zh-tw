---
title: /REBASE
ms.date: 11/04/2016
f1_keywords:
- /rebase
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
ms.openlocfilehash: 42cbcb911fcd0aa7753d84aae5523d28371b9972
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319196"
---
# <a name="rebase"></a>/REBASE

```
/REBASE[:modifiers]
```

## <a name="remarks"></a>備註

這個選項會設定指定檔案的基底位址。 EDITBIN 會指派新的基底地址，無條件進位到最接近 64 KB 的每個檔案的大小根據連續的位址空間。 如需基底地址的詳細資訊，請參閱[基底位址](base-base-address.md)（/ 基底） 連結器選項。

指定程式的可執行檔和中的 Dll*檔案*EDITBIN 命令列中的順序將依據的為引數。 您可以選擇性地指定一或多個*修飾詞*，每個以逗號分隔 (**，**):

|修飾詞|動作|
|--------------|------------|
|**BASE=**<em>address</em>|提供的起始位址重新指派基底位址的檔案。 指定*地址*以十進位數或 C 語言表示法。 如果未指定基底，啟動基底地址的預設值為 0x400000。 如果清單已使用的基底必須指定，並*地址*設定的基底的位址範圍的結尾。|
|**BASEFILE**|建立名為 COFFBASE 的檔案。TXT，這是文字檔案中所連結的預期的格式/基底選項。|
|**向下**|會告知 EDITBIN 重新指派基底位址則是往下的從結束位址。 指定時，使用位於以下位址範圍的結尾可能最高的位址中的第一個檔案的順序重新指派檔案。 基底必須搭配下，以確保足夠的位址空間為基礎的檔案。 若要判斷指定的檔案所需的位址空間，/REBASE EDITBIN 執行的檔案，並加入顯示的總大小 64KB。|

## <a name="see-also"></a>另請參閱

[EDITBIN 選項](editbin-options.md)
