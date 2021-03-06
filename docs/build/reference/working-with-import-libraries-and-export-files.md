---
title: 與匯入程式庫和匯出檔案一起使用
ms.date: 11/04/2016
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
ms.openlocfilehash: 6f6f2d5c48c63ba6d8a8a7f67a98b949b32a8afa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316505"
---
# <a name="working-with-import-libraries-and-export-files"></a>與匯入程式庫和匯出檔案一起使用

您可以使用 LIB /DEF 選項，來建立匯入程式庫和匯出檔案。 連結會使用匯出檔建置的程式包含匯出 （通常是動態連結程式庫 (DLL)），並使用匯入程式庫來解析參考匯出的其他程式。

請注意，是否您建立您匯入程式庫中第一步，建立.dll 之前，您必須傳遞同一組物件檔案建置.dll 時為您成功建置匯入程式庫時。

在大部分情況下，您不需要使用 LIB 來建立您的匯入程式庫。 當您連結包含匯出的程式 （可執行檔或 DLL） 時，連結會自動建立描述匯出匯入程式庫。 稍後，當您連結參考匯出的程式，您會指定匯入程式庫。

不過，當 DLL 會匯出至它也會從匯入的程式，是否直接或間接，您必須使用 LIB 建立其中一個匯入程式庫。 當程式庫建立匯入程式庫時，它也會建立匯出檔案。 連結的 dll 檔時，您必須使用匯出檔。

## <a name="see-also"></a>另請參閱

[LIB 參考](lib-reference.md)
