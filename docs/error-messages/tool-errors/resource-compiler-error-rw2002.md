---
title: 資源編譯器錯誤 RW2002
ms.date: 11/04/2016
f1_keywords:
- RW2002
helpviewer_keywords:
- RW2002
ms.assetid: b1d1a49b-b50b-4b0b-9f09-c7762e2dbe8f
ms.openlocfilehash: 9c5c2824778a679627bd3008276849890f43ac7e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190686"
---
# <a name="resource-compiler-error-rw2002"></a>資源編譯器錯誤 RW2002

剖析錯誤

### <a name="to-fix-by-checking-the-following-possible-causes"></a>透過檢查下列可能原因進行修正

1. **需要加速器類型（ASCII 或 VIRTKEY）**

   `type` ACCELERATORS **陳述式中的** 欄位必須包含 ASCII 或 VIRTKEY 值。

1. **在快速鍵對應表中開始預期**

   **BEGIN** 關鍵字必須緊接在 **ACCELERATORS** 關鍵字之後。

1. **在對話方塊中開始預期**

   **BEGIN**關鍵字必須緊接在**DIALOG**關鍵字之後。

1. **功能表中的預期開始**

   **BEGIN** 關鍵字必須緊接在 **MENU** 關鍵字之後。

1. **預期會在 RCData 中開始**

   **BEGIN** 關鍵字必須緊接在 **RCDATA** 關鍵字之後。

1. **字串資料表中應有 BEGIN 關鍵字**

   **BEGIN**關鍵字必須緊接在**STRINGTABLE**關鍵字之後。

1. **無法重複使用字串常數**

   在**STRINGTABLE**語句中，您會使用相同的值兩次。 請確定您不會混用重迭的十進位和十六進位值。 **STRINGTABLE**中的每個識別碼都必須是唯一的。 為了達到最高效率，請使用以16的倍數開始的連續常數。

1. **控制字元超出範圍 [^ A-^ Z]**

   **ACCELERATORS** 陳述式中的控制字元無效。 插入號 ( **^** ) 後的字元必須介於 A 與 Z (含) 之間。

1. **不允許空的功能表**

   在**功能表**語句中定義任何功能表項目之前，會出現**END**關鍵字。 資源編譯器不允許空的功能表。 請確定您在**MENU**語句中沒有任何左引號。

1. **對話方塊中預期的結尾**

   **End**關鍵字必須發生在**DIALOG**語句的結尾。 請確定先前的語句中沒有左邊的引號。

1. **功能表中預期的結尾**

   **END** 關鍵字必須放在 **MENU** 陳述式結尾。 請確定您沒有不完整的引號或不成對的 **BEGIN** 和 **END** 陳述式。

1. **快速鍵對應表中必須是逗號**

   資源編譯器需要 `event` ACCELERATORS *陳述式的* 與 **idvalue** 欄位之間有一個逗號。

1. **需要的控制項類別名稱**

   **DIALOG**語句中**CONTROL**語句的 `class` 欄位必須是下列其中一種類型：按鈕、COMBOBOX、編輯、LISTBOX、捲軸、靜態或使用者定義。 請確定類別的拼寫正確。

1. **預期的字型名稱**

   *DIALOG* 陳述式中 FONT 選項的 **typeface** 欄位必須是以雙引號括住的 ASCII 字串。 此欄位指定字型的名稱。

1. **Menuitem 的預期識別碼值**

   **MENU** 陳述式必須包含 *menuID* 欄位，指定識別功能表資源的名稱或數字。

1. **需要的功能表字串**

   每個 **MENUITEM** 和 **POPUP** 陳述式皆必須包含「文字」 欄位，該欄位為以雙引號括住並指定功能表項目或快顯功能表名稱的字串。 **MENUITEM 分隔符號**語句不需要加上引號的字串。

1. **預期的數值命令值**

   資源編譯器在**快速鍵**語句中預期會有數值*idvalue*欄位。 請確定您已使用 `#define` 常數來指定值，且常數的拼寫正確。

1. **字串資料表中必須有數值常數**

   數值常數，定義在 `#define` 陳述式中，必須緊接在 **STRINGTABLE** 陳述式的 **BEGIN** 關鍵字之後。

1. **預期的數值點大小**

   *DIALOG* 陳述式之字型選項的 [點數大小] 欄位必須是整數點大小值。

1. **預期的數值對話方塊常數**

   DIALOG 語句需要 [x]、[ *y]、[width*] 和 [ *height* **]** 欄位的整數值。 請確定這些值都包含在**DIALOG**關鍵字之後，而且不是負數。

1. **STRINGTABLE 中需要的字串**

   在 *STRINGTABLE* 陳述式中的每個 **stringid** 值後面必須是字串。

1. **預期的字串或常數快速鍵命令**

   資源編譯器無法判斷為加速器所設定的按鍵類型。 `event` ACCELERATORS **陳述式中的** 欄位可能無效。

1. **需要 ID 的數位**

   在**DIALOG**語句中，控制項語句的 `id` 欄位應為數字。 請確定您有控制項識別碼的數位或 `#define` 語句。

1. **對話方塊類別中必須有引號的字串**

   `class` DIALOG **陳述式中 CLASS 選項的** 欄位必須是以雙引號括住的整數或字串。

1. **對話方塊標題中需要有引號的字串**

   `captiontext` DIALOG **陳述式中 CAPTION 選項的** 欄位必須是以雙引號括住的 ASCII 字串。

1. **找不到檔案：檔案名**

   找不到資源編譯器命令列中所指定的檔案。 請確認是否已將檔案移至另一個目錄，以及是否正確地輸入檔名或路徑。 系統會使用**INCLUDE**環境變數或 Visual Studio 設定（如果有的話）來搜尋檔案。

1. **字型名稱必須是序數**

   字型語句中的*pointsize*欄位必須是整數，而不是字串。

1. **不正確快速鍵**

   `event` ACCELERATORS **陳述式中的** 欄位無法辨識，或長度超過兩個字元。

1. **不正確快速鍵類型（ASCII 或 VIRTKEY）**

   `type` ACCELERATORS **陳述式中的** 欄位必須包含 ASCII 或 VIRTKEY 值。

1. **不正確控制字元**

   **ACCELERATORS** 陳述式中的控制字元無效。 有效的控制字元是由插入號（^）後面的一個字母（僅限）所組成。

1. **不正確控制項類型**

   **DIALOG**語句中的每個控制語句都必須是下列其中一項： CHECKBOX、COMBOBOX、CONTROL、CTEXT、DEFPUSHBUTTON、EDITTEXT、群組方塊、圖示、LISTBOX、LTEXT、按鈕、選項按鈕、RTEXT、捲軸。 請確定這些控制語句的拼寫正確。

1. **不正確類型**

   資源類型不是在 WINDOWS .h 檔案中定義的類型。

1. **控制項中預期的文字字串或序數**

   **DIALOG**語句中**control**語句的*文字*欄位必須是文字字串或控制項類型的序數參考。 如果使用序數，請確定控制項具有 `#define` 陳述式。

1. **不成對的括弧**

   請確定您已關閉**DIALOG**語句中的每個左括弧。

1. **RCData 中有未預期的值**

   *RCDATA* 陳述式中的 **raw-data** 值必須是整數或字串，並以逗號區隔。 請確定您未遺漏逗號或字串周圍的引號。

1. **未知的功能表子類型**

   **MENU**語句的*專案定義*欄位只能包含**MENUITEM**和**POPUP**語句。
