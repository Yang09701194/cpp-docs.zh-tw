---
title: 例外狀況：從您自己的函式擲回例外狀況
ms.date: 11/04/2016
helpviewer_keywords:
- throwing exceptions [MFC], from functions
- functions [MFC], throwing exceptions
- exceptions [MFC], throwing
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
ms.openlocfilehash: 6484594df7636fd52ac46ab1cc212c8e2ec0278e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359282"
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>例外狀況：從您自己的函式擲回例外狀況

可以只使用 MFC 例外狀況處理範例，來攔截 MFC 或其他程式庫中的函式所擲回的例外狀況。 除了攔截程式庫程式碼擲回的例外狀況之外，如果您正在撰寫可能發生例外狀況的函式，還可以從您自己的程式碼擲回例外狀況。

引發異常時,將停止執行當前函數並直接跳轉到最內範圍異常幀的**catch**塊。 例外狀況機制會略過從函式的正常結束路徑。 因此，您必須確定刪除在正常結束要刪除的記憶體區塊。

#### <a name="to-throw-an-exception"></a>擲回例外狀況

1. 使用其中一個 MFC helper 函式，例如 `AfxThrowMemoryException`。 這些函式會擲回預先配置的適當類型的例外狀況物件。

   在下列範例中，如果任一配置失敗，函式會嘗試配置兩個記憶體區塊並擲回例外狀況：

   [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]

   如果第一個配置失敗，您可以只擲回記憶體例外狀況。 如果第一個配置成功，但是第二個失敗，您必須在擲回例外狀況之前釋出第一個配置區塊。 如果兩個配置都成功，您可以正常繼續進行並在結束函式時釋出區塊。

     - 或 -

1. 使用使用者定義的例外狀況來指出問題的狀況。 您可以擲回任何類型的項目，甚至整個類別作為您的例外狀況。

   如果發生失敗，下列範例會嘗試透過聲波裝置播放音效並擲回例外狀況。

   [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]

> [!NOTE]
> MFC 的例外狀況預設處理僅適用於 `CException` 物件的指標 (以及 `CException` 衍生類別的物件)。 上述範例會略過 MFC 的例外狀況機制。

## <a name="see-also"></a>另請參閱

[例外狀況處理](../mfc/exception-handling-in-mfc.md)
