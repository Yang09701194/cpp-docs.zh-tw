---
title: C 執行階段錯誤 R6025
ms.date: 11/04/2016
f1_keywords:
- R6025
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
ms.openlocfilehash: d5edb08278b7b6b9b3eb62e92fc04410f96a8f09
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075120"
---
# <a name="c-runtime-error-r6025"></a>C 執行階段錯誤 R6025

純虛擬函式呼叫

> [!NOTE]
> 如果您在執行應用程式時遇到此錯誤訊息，則應用程式已關閉，因為它有內部問題。 此錯誤最常見的原因是應用程式中的錯誤或損毀的安裝。
>
> 您可以嘗試進行下列步驟來修正這個錯誤：
>
> - 使用 [**控制台**] 中的 [**應用程式和功能**] 或 [**程式和功能**] 頁面修復或重新安裝程式。
> - 在 [**控制台**] 中選取 [軟體更新] **Windows Update** 。
> - 檢查應用程式的更新版本。 如果問題持續發生，請洽詢應用程式廠商。

**程式設計人員的資訊**

未具現化物件來處理純虛擬函式呼叫。

這個錯誤的原因是透過轉換成衍生類別的型別所建立的指標來呼叫抽象基類中的虛擬函式，但實際上是基類的指標。 當在基底類別的結構中建立**void** <strong>\*</strong>時，從**void** <strong>\*</strong>轉換成類別的指標時，就會發生這種情況。
