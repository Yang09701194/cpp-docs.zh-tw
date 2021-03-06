---
title: Microsoft C++ 語言一致性表
description: Microsoft 表C++按 Visual Studio 版本進行的一致性更新。
ms.date: 03/17/2020
ms.technology: cpp-language
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
author: corob-msft
ms.author: corob
ms.openlocfilehash: 18f8db28fab83f795baced82a346f07d73256716
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365229"
---
# <a name="microsoft-c-language-conformance-table"></a>Microsoft C++ 語言一致性表

Visual Studio (MSVC) 中的 Microsoft C++編譯器的標準符合性是一項正在進行中的工作。 以下是我們的 ISO 標準 C++ Visual Studio 版本的語言和庫一致性的摘要。 每個編譯器和標準庫功能名稱連結到 ISO 標準C++建議檔,該紙描述了該功能(如果發佈時可用)。 "**支援"** 列列出了首次顯示對該功能的支援的視覺化工作室版本。

有關 Visual Studio 2017 或 Visual Studio 2019 MSVC 符合性改進的詳細資訊,請參閱[Visual Studio 中 C++一致性改進](cpp-conformance-improvements.md)。 有關其他更改的清單,請參閱[可視化工作室中視覺C++的新增功能](what-s-new-for-visual-cpp-in-visual-studio.md)。 如需舊版的一致性變更，請參閱 [Visual C++ 變更歷程記錄](../porting/visual-cpp-change-history-2003-2015.md)和[從 2003 到 2015 的 Visual C++ 新功能](../porting/visual-cpp-what-s-new-2003-through-2015.md)。 如需 C++ 小組發出的最新消息，請瀏覽 [小組部落格](https://devblogs.microsoft.com/cppblog/) \(英文\)。

> [!NOTE]
> Visual Studio 2015、Visual Studio 2017 與 Visual Studio 2019 之間沒有二進位檔重大變更。 有關詳細資訊,請參閱[Visual Studio 2015、2017 和 2019 之間的C++二進位兼容性](../porting/binary-compat-2015-2017.md)

## <a name="compiler-features"></a>編譯器功能

|  |  |
|--|--|
| __C++03/11 核心語言功能__ | __支援__ |
| &nbsp;&nbsp;其他所有項目 | VS 2015 <sup>[A](#note_A)</sup> |
| &nbsp;&nbsp;兩階段名稱查詢 | VS 2017 15.7 <sup>[B](#note_B)</sup> |
| &nbsp;&nbsp;[N2634 運算式 SFINAE](https://wg21.link/N2634) | VS 2017 15.7 |
| &nbsp;&nbsp;[N1653 C99 前置處理器](https://wg21.link/N1653) | 部分 <sup>[C](#note_C)</sup> |
| __C++14 核心語言功能__ | __支援__ |
| &nbsp;&nbsp;[N3323 調整內容轉換的描述](https://wg21.link/N3323) | VS 2013 |
| &nbsp;&nbsp;[N3472 二進位常值](https://wg21.link/N3472) | VS 2015 |
| &nbsp;&nbsp;[N3638 auto 和 decltype(auto) 傳回型別](https://wg21.link/n3638) | VS 2015 |
| &nbsp;&nbsp;[N3648 init 擷取](https://wg21.link/n3648) | VS 2015 |
| &nbsp;&nbsp;[N3649 泛型 Lambda](https://wg21.link/n3649) | VS 2015 |
| &nbsp;&nbsp;[N3760\[\[棄\]\]用 屬性](https://wg21.link/n3760) | VS 2015 |
| &nbsp;&nbsp;[N3778 大小處理](https://wg21.link/n3778) | VS 2015 |
| &nbsp;&nbsp;[N3781 數字分隔符號](https://wg21.link/n3781) | VS 2015 |
| &nbsp;&nbsp;[N3651 變數範本](https://wg21.link/n3651) | VS 2015.2 |
| &nbsp;&nbsp;[N3652 擴充的 constexpr](https://wg21.link/n3652) | VS 2017 15.0 |
| &nbsp;&nbsp;[N3653 針對彙總的預設成員初始設定式](https://wg21.link/n3653) \(英文\) | VS 2017 15.0 |
| __C++17 核心語言功能__ | __支援__ |
| &nbsp;&nbsp;[N4086 移除三併詞](https://wg21.link/n4086) | VS 2010 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N3922 使用 braced-init-list 的 auto 新規則](https://wg21.link/n3922) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4051 範本 template 參數中的 typename](https://wg21.link/n4051) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4266 命名空間和枚舉器的屬性](https://wg21.link/n4266) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4267 u8字元文字](https://wg21.link/n4267) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4230 巢狀命名空間定義](https://wg21.link/n4230) | VS 2015.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N3928 Terse static_assert](https://wg21.link/n3928) | VS 2017 15.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0184R0 通用的範圍架構 for 迴圈](https://wg21.link/p0184r0) | VS 2017 15.0 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0188R1\[\[\]\]下降 屬性](https://wg21.link/p0188r1) | VS 2017 15.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0001R1 移除 register 關鍵字](https://wg21.link/p0001r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0002R1 移除 bool 的 operator++](https://wg21.link/p0002r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0018R3 依據值擷取 *this](https://wg21.link/p0018r3) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0028R4 使用不重複的屬性命名空間](https://wg21.link/p0028r4) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0061R1 \_ \_has_include](https://wg21.link/p0061r1) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0138R2 整數的固定列舉直接清單初始化](https://wg21.link/p0138r2) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0170R1 constexpr Lambda](https://wg21.link/p0170r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0189R1\[\[\]\]無 棄屬性](https://wg21.link/p0189r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0212R1 \[ \[ \] \] maybe_unused屬性](https://wg21.link/p0212r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0217R3 結構化的繫結](https://wg21.link/p0217r3) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0292R2 constexpr if 陳述式](https://wg21.link/p0292r2) | VS 2017 15.3 <sup>[D](#note_D)</sup> |
| &nbsp;&nbsp;[P0305R1 使用初始設定式的選取範圍陳述式](https://wg21.link/p0305r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0245R1 Hexfloat 常值](https://wg21.link/p0245r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N4268 允許多個非類型範本引數](https://wg21.link/n4268) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N4295 摺疊運算式](https://wg21.link/n4295) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0003R5 移除動態例外狀況規格](https://wg21.link/p0003r5) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0012R1 新增 noexcept 型別系統](https://wg21.link/p0012r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0035R4 過度對齊的動態記憶體配置](https://wg21.link/p0035r4) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0386R2 內嵌變數](https://wg21.link/p0386r2) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0522R0 範本 template 參數與相容引數的比對](https://wg21.link/p0522r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0036R0 移除部分空白一元摺疊](https://wg21.link/p0036r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N4261 修正限定性條件轉換](https://wg21.link/n4261) | VS 2017 15.7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0017R1 擴充的彙總初始化](https://wg21.link/p0017r1) | VS 2017 15.7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0091R3 類別範本的範本引數推斷](https://wg21.link/p0091r3)<br/>&nbsp;&nbsp;[P0512R0 類別樣板引數推斷問題](https://wg21.link/p0512r0) \(英文\) | VS 2017 15.7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0127R2 使用 auto 宣告非類型範本參數](https://wg21.link/p0127r2) | VS 2017 15.7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0135R1 保證的複製省略](https://wg21.link/p0135r1) | VS 2017 15.6 |
| &nbsp;&nbsp;[P0136R1 改寫繼承建構函式](https://wg21.link/p0136r1) | VS 2017 15.7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0137R1 std::launder](https://wg21.link/p0137r1) | VS 2017 15.7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0145R3 調整運算式評估順序](https://wg21.link/p0145r3)<br/>&nbsp;&nbsp;[P0400R0 函式引數的評估順序](https://wg21.link/p0400r0) \(英文\) | VS 2017 15.7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0195R2 using-declaration 的套件延伸模組](https://wg21.link/p0195r2) | VS 2017 15.7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0283R2 略過無法辨認的屬性](https://wg21.link/p0283r2) | VS 2015 <sup>[14](#note_14)</sup> |
| __C++17 核心語言功能(缺陷報告)__ | __支援__ |
| &nbsp;&nbsp;[P0702R1 修正初始設定式清單 ctor 的類別樣板引數推斷](https://wg21.link/p0702r1) \(英文\) | VS 2017 15.7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0961R1 放寬結構化繫結的自訂點尋找規則](https://wg21.link/p0961r1) \(英文\) | VS 2019 16.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0969R0 允許可存取成員進行結構化繫結](https://wg21.link/p0969r0) | VS 2019 16.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0588R1 簡化隱含的 Lambda 擷取](https://wg21.link/p0588r1) | VS 2019 16.4 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P1771R1\[\[\]\]不 丟棄構造函數](https://wg21.link/p1771r1) | VS 2019 16.4 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P1825R0 P0527R1 和 P1155R3 的合併措辭,更隱式移動](https://wg21.link/p1825r0) | VS 2019 16.4 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0929R2 檢查抽象類別型別](https://wg21.link/P0929R2) | 否 |
| &nbsp;&nbsp;[P0962R2 放寬 range-for 迴圈的自訂點尋找規則](https://wg21.link/p0962r1) | 否 |
| &nbsp;&nbsp;[P0859R0 CWG 1581:何時定義輔流成員函數](https://wg21.link/p0859r0) | 否 |
| &nbsp;&nbsp;[P1009R2 陣列大小在 new-expressions 中減少](https://wg21.link/P1009R2) | 否 |
| &nbsp;&nbsp;[P1286R2 Contra CWG DR1778](https://wg21.link/P1286R2) | 否 |
| __C++20 核心語言功能__ | __支援__ |
| &nbsp;&nbsp;[P0704R1 修正針對成員的常數左值 ref 限定指標](https://wg21.link/p0704r1) \(英文\) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1041R4 讓 char16_t/char32_t 字串常值成為 UTF-16/32](https://wg21.link/P1041R4) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1330R0 變更 constexpr 內的作用中聯集成員](https://wg21.link/P1330R0) | VS 2017 15.0 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0972R0 noexcept For \<chrono> zero(), min(), max()](https://wg21.link/P0972R0) | VS 2017 15.7 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0515R3 三向 (太空船) 比較運算子 <=>](https://wg21.link/P0515R3) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0941R2 功能測試巨集](https://wg21.link/P0941R2) | VS 2019 16.0 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1008R1 禁止使用使用者宣告建構函式來彙總](https://wg21.link/P1008R1) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0329R4 指定的初始化](https://wg21.link/p0329r4) \(英文\) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0846R0 不可見的 ADL 與函式範本](https://wg21.link/P0846R0) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0409R2 允許 lambda\[捕獲 |,這\]](https://wg21.link/p0409r2) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0428R2 針對泛型 Lambda 的熟悉範本語法](https://wg21.link/p0428r2) \(英文\) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0624R2 Default 預設可建構與無狀態 lambdas](https://wg21.link/P0624R2) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0780R2 允許 lambda init-capture 中的封裝展開](https://wg21.link/P0780R2) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0806R2 通過\[=\]](https://wg21.link/P0806R2) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1120R0 <=> 與其他比較運算子的一致性改良](https://wg21.link/P1120R0) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1185R2 \< = \> !*](https://wg21.link/P1185R2) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0734R0 概念](https://wg21.link/P0734R0) \(英文\) | VS 2019 16.3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0857R0 修正限制式中的功能差距](https://wg21.link/P0857R0) | VS 2019 16.3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1084R2 今天的 return-type-requirements 不足](https://wg21.link/P1084R2) | VS 2019 16.3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0892R2 條件式明確](https://wg21.link/P0892R2) | VS 2019 16.4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1091R3 延伸結構化繫結讓它看起來比較像是變數宣告](https://wg21.link/P1091R3) | VS 2019 16.4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1099R5 使用枚舉](https://wg21.link/P1099R5) | VS 2019 16.4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1186R3 您實際使用時間\<=>](https://wg21.link/P1186R3) | VS 2019 16.4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1630R1太空船需要調子](https://wg21.link/P1630R1) | VS 2019 16.4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0306R4\_\_\_\_新增 逗號省略和逗號刪除VA_OPT](https://wg21.link/P0306R4) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0614R1 具有初始設定式的範圍型 for-loops](https://wg21.link/P0614R1) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0683R1 針對位元欄位的預設成員初始設定式](https://wg21.link/P0683R1) \(英文\) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1002R1 constexpr 函式中的 try-catch 區塊](https://wg21.link/P1002R1) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1161R3 在下標表示式中棄用逗號運算符號](https://wg21.link/P1161R3) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1301R4\[\[無棄置("消息")\]\]](https://wg21.link/P1301R4) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1703R1 識別標頭單元匯入需要完全預處理](https://wg21.link/P1703R1) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1946R0 允許按值進行預設比較](https://wg21.link/P1946R0) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0641R2 與預設複本建構函式的常數不符](https://wg21.link/P0641R2) | 部分 |
| &nbsp;&nbsp;[P0912R5 協同程式](https://wg21.link/P0912R5) | 部分 |
| &nbsp;&nbsp;[P1103R3 模組](https://wg21.link/P1103R3) | 部分 |
| &nbsp;&nbsp;[P0315R4 允許為評估之上下文中的 lambdas](https://wg21.link/P0315R4) | 否 |
| &nbsp;&nbsp;[P0388R4 允許轉換為未知的陣列](https://wg21.link/P0388R4) | 否 |
| &nbsp;&nbsp;[P0479R5 \[ \[ \] \]\[\[可能\]\]與不太可能的屬性](https://wg21.link/P0479R5) | 否 |
| &nbsp;&nbsp;[P0634R3 已使用型別名稱完成！](https://wg21.link/P0634R3) | 否 |
| &nbsp;&nbsp;[P0692R1 特殊化上的寬鬆存取檢查](https://wg21.link/P0692R1) | 否 |
| &nbsp;&nbsp;[P0722R3 可變大小類別的有效率大小調整刪除](https://wg21.link/P0722R3) | 否 |
| &nbsp;&nbsp;[P0732R2 非型別範本參數中的類別型別](https://wg21.link/P0732R2) | 否 |
| &nbsp;&nbsp;[P0735R1 memory_order_consume與發佈序列的互動](https://wg21.link/P0735R1) | 否 |
| &nbsp;&nbsp;[P0784R7 更多缺點容器](https://wg21.link/P0784R7) | 否 |
| &nbsp;&nbsp;[P0840R2 \[ \[ \] \] no_unique_address屬性](https://wg21.link/P0840R2) | 否 |
| &nbsp;&nbsp;[P0848R3 有條件地瑣碎的特殊成員函數](https://wg21.link/P0848R3) | 否 |
| &nbsp;&nbsp;[P0960R3 允許從以括弧括住的值初始化彙總](https://wg21.link/P0960R3) | 否 |
| &nbsp;&nbsp;[P1064R0 允許常數運算式中的虛擬函式呼叫](https://wg21.link/P1064R0) | 否 |
| &nbsp;&nbsp;[P1073R3 即時運算函式](https://wg21.link/P1073R3) | 否 |
| &nbsp;&nbsp;[P1094R2 巢狀內嵌命名空間](https://wg21.link/P1094R2) | 否 |
| &nbsp;&nbsp;[P1139R2 與 ISO 10646 有關的位址選字問題](https://wg21.link/P1139R2) | 否 |
| &nbsp;&nbsp;[P1141R2 受限宣告的另一個方法](https://wg21.link/P1141R2) | 否 |
| &nbsp;&nbsp;[P1143R2 康斯汀特](https://wg21.link/P1143R2) | 否 |
| &nbsp;&nbsp;[P1152R4 棄用揮發性](https://wg21.link/P1152R4) | 否 |
| &nbsp;&nbsp;[P1236R1 帶正負號的整數是兩個互補數](https://wg21.link/P1236R1) | 否 |
| &nbsp;&nbsp;[P1327R1 允許常數運算式中的 dynamic_cast、多形 typeid](https://wg21.link/P1327R1) | 否 |
| &nbsp;&nbsp;[P1331R2 允許在 constexpr 上下文中進行微不足道的預設初始化](https://wg21.link/P1331R2) | 否 |
| &nbsp;&nbsp;[P1353R0 缺少功能測試巨集](https://wg21.link/P1353R0) | 否 |
| &nbsp;&nbsp;[P1381R1 結構化繫結的參考擷取](https://wg21.link/P1381R1) | 否 |
| &nbsp;&nbsp;[P1452R2 關於傳回類型要求的不均勻語義](https://wg21.link/P1452R2) | 否 |
| &nbsp;&nbsp;[P1616R1 使用帶有約束範本的無約束 TP](https://wg21.link/P1616R1) | 否 |
| &nbsp;&nbsp;[P1668R1 允許在輔流功能中進行未評估的內聯裝配](https://wg21.link/P1668R1) | 否 |
| &nbsp;&nbsp;[P1766R1 緩解小模組疾病](https://wg21.link/P1766R1) | 否 |
| &nbsp;&nbsp;[P1811R0 放寬重新匯出穩健性的重新定義限制](https://wg21.link/P1811R0) | 否 |
| &nbsp;&nbsp;[P1814R0 CTAD 別名樣本](https://wg21.link/P1814R0) | 否 |
| &nbsp;&nbsp;[P1816R0 CTAD 用於集合合](https://wg21.link/P1816R0) | 否 |
| &nbsp;&nbsp;[P1874R1 模組中非局部變數的動態初始化順序](https://wg21.link/P1874R1) | 否 |
| &nbsp;&nbsp;[P1907R1 與非類型樣本參數不一致](https://wg21.link/P1907R1) | 否 |
| &nbsp;&nbsp;[P1971R0 NB 評論的核心變化在 2019 年 11 月 (貝爾法斯特) 會議上](https://wg21.link/P1971R0) | 否 |
| &nbsp;&nbsp;[P1972R0 US105 在形成函數指標時檢查非範本約束的滿意度](https://wg21.link/P1972R0) | 否 |
| &nbsp;&nbsp;[P1975R0 修正括弧聚合初始化的措辭](https://wg21.link/P1975R0) | 否 |
| &nbsp;&nbsp;[P1979R0 解析度至 US086](https://wg21.link/P1979R0) | 否 |
| &nbsp;&nbsp;[P1980R0 CA096:非依賴需求子項的聲明匹配](https://wg21.link/P1980R0) | 否 |

## <a name="standard-library-features"></a>標準程式庫功能

|  |  |
|--|--|
| __C++20 標準庫功能__ | __支援__ |
| &nbsp;&nbsp;[P0809R0 比較未排序的容器](https://wg21.link/p0809r0) | VS 2010 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0858R0 Constexpr 迭代器需求](https://wg21.link/p0858r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0777R1 避免不必要的 Decay](https://wg21.link/p0777r1) | VS 2017 15.7 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1164R1 使create_directory() 直觀](https://wg21.link/P1164R1) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0550R2 remove_cvref](https://wg21.link/p0550r2) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0318R1 unwrap_reference、unwrap_ref_decay](https://wg21.link/p0318r1) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0457R2 basic_string/basic_string_view 的 starts_with()/ends_with()](https://wg21.link/p0457r2) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0458R2 具順序與不具順序關聯容器的 contains()](https://wg21.link/p0458r2) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0646R1 list/forward_list remove()/remove_if()/unique() 傳回 size_type](https://wg21.link/p0646r1) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0769R2 shift_left()、shift_right()](https://wg21.link/p0769r2) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0887R1 type_identity](https://wg21.link/p0887r1) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0020R6 atomic\<float>、atomic\<double>、atomic\<long double>](https://wg21.link/p0020r6) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0463R1 位元組順序](https://wg21.link/p0463r1) \(英文\) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0482R6 char8_t:UTF-8 字元和字串的類型](https://wg21.link/P0482R6) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0600R1\[\[\]\]無 棄,適用於 STL,第 1 部分](https://wg21.link/p0600r1) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0653R2 to_address()](https://wg21.link/p0653r2) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0754R2 \<version>](https://wg21.link/p0754r2) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0771R1 noexcept 適用於 std::function 的移動建構函式](https://wg21.link/P0771R1) | VS 2019 16.2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0487R1 修正運算子>>(basic_istream&, CharT*)](https://wg21.link/P0487R1) | VS 2019 16.3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0616R0 在 \<numeric> 中使用 move()](https://wg21.link/p0616r0) | VS 2019 16.3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0758R1 is_nothrow_convertible](https://wg21.link/P0758R1) | VS 2019 16.3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0898R3 標準程式庫概念](https://wg21.link/P0898R3) | VS 2019 16.3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0919R3 未具順序之限制式的異質查閱](https://wg21.link/P0919R3) | VS 2019 16.3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1754R1 將概念重新命名為standard_case](https://wg21.link/P1754R1) | VS 2019 16.4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0325R4 to_array來自LFTS,提供更新](https://wg21.link/P0325R4) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0340R3 SFINAE 友善 underlying_type](https://wg21.link/P0340R3) | VS 2019 16.5 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0356R5 bind_front()](https://wg21.link/P0356R5) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0439R0 列舉類別 memory_order](https://wg21.link/p0439r0) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0553R4\<位元>旋轉和計數功能](https://wg21.link/P0553R4) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0556R3\<位> ispow2()、ceil2()、地板 2()、log2p1()](https://wg21.link/P0556R3) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0595R2 is_constant_evaluated()](https://wg21.link/P0595R2) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0631R8\<數位>數學常量](https://wg21.link/P0631R8) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0738R2 istream_iterator 清除](https://wg21.link/P0738R2) | VS 2019 16.5 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0767R1 淘汰 is_pod](https://wg21.link/P0767R1) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0966R1 string::reserve() 不應該壓縮](https://wg21.link/P0966R1) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1209R0 erase_if()、erase()](https://wg21.link/P1209R0) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1227R2 帶正負號的 std::ssize()、不帶正負號的 span::size()](https://wg21.link/P1227R2) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1355R2 窄合約 ceil2()](https://wg21.link/P1355R2) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1357R1 is_bounded_array、is_unbounded_array](https://wg21.link/P1357R1) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1612R1 重新置放\<端對位>](https://wg21.link/P1612R1) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1651R0 bind_front() 不應解包reference_wrapper](https://wg21.link/P1651R0) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1690R1 未訂購容器的精煉異構查找](https://wg21.link/P1690R1) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1902R1 缺少功能測試宏 2017-2019](https://wg21.link/P1902R1) | VS 2019 16.5 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0019R8 atomic_ref](https://wg21.link/P0019R8) | 否 |
| &nbsp;&nbsp;[P0053R7 \<syncstream>](https://wg21.link/p0053r7)<br/>&nbsp;&nbsp;[P0753R2 osyncstream 操作工具](https://wg21.link/p0753r2) | 否 |
| &nbsp;&nbsp;[P0122R7 \<span>](https://wg21.link/p0122r7) | 否 |
| &nbsp;&nbsp;[P0202R3 \<algorithm> 和 exchange() 的 constexpr](https://wg21.link/p0202r3) | 否 |
| &nbsp;&nbsp;[P0339R6 polymorphic_allocator<>](https://wg21.link/P0339R6) | 否 |
| &nbsp;&nbsp;[P0355R7 \<chrono> 行事曆和時區](https://wg21.link/p0355r7) | 否 |
| &nbsp;&nbsp;[P0357R3 支援 reference_wrapper 中的不完整型別](https://wg21.link/P0357R3) | 否 |
| &nbsp;&nbsp;[P0415R1 \<complex> 的 constexpr (再次)](https://wg21.link/p0415r1) | 否 |
| &nbsp;&nbsp;[P0475R1 分段建構的保證複製省略](https://wg21.link/P0475R1) | 否 |
| &nbsp;&nbsp;[P0476R2\<位>bit_cast](https://wg21.link/P0476R2) | 否 |
| &nbsp;&nbsp;[P0528R3 具有填補位元的不可部分完成 Compare-And-Exchange](https://wg21.link/P0528R3) | 否 |
| &nbsp;&nbsp;[P0591R4 Uses-Allocator 建構的公用程式函式](https://wg21.link/P0591R4) | 否 |
| &nbsp;&nbsp;[P0608R3 改進變數的轉換建構函式/指派](https://wg21.link/P0608R3) | 否 |
| &nbsp;&nbsp;[P0619R4 移除 C++20 中的 C++17 過時功能](https://wg21.link/P0619R4) | 否 |
| &nbsp;&nbsp;[P0653R2 to_address()](https://wg21.link/p0653r2) | 否 |
| &nbsp;&nbsp;[P0655R1\<存取 R>()](https://wg21.link/P0655R1) | 否 |
| &nbsp;&nbsp;[P0674R1 適用於陣列的 make_shared()](https://wg21.link/p0674r1) \(英文\) | 否 |
| &nbsp;&nbsp;[P0718R2 atomic\<shared_ptr\<T>>、atomic\<weak_ptr\<T>>](https://wg21.link/p0718r2) | 否 |
| &nbsp;&nbsp;[P0768R1 太空船比較運算子的庫支援\<=>](https://wg21.link/p0768r1) | 否 |
| &nbsp;&nbsp;[P0811R3 midpoint()、lerp()](https://wg21.link/P0811R3) | 否 |
| &nbsp;&nbsp;[P0879R0 constexpr 適用於交換函式](https://wg21.link/P0879R0) | 否 |
| &nbsp;&nbsp;[P0896R4 \<範圍\>](https://wg21.link/P0896R4) | 否 |
| &nbsp;&nbsp;[P0912R5 協同程式的程式庫支援](https://wg21.link/P0912R5) | 否 |
| &nbsp;&nbsp;[P0920R2 預先計算雜湊值查閱](https://wg21.link/P0920R2) | 否 |
| &nbsp;&nbsp;[P0935R0 杜絕不必要的明確預設建構函式](https://wg21.link/P0935R0) | 否 |
| &nbsp;&nbsp;[P1001R2 execution::unseq](https://wg21.link/P1001R2) | 否 |
| &nbsp;&nbsp;[P1006R1 constexpr 適用於 pointer_traits<T*>::pointer_to()](https://wg21.link/P1006R1) | 否 |
| &nbsp;&nbsp;[P1007R3 assume_aligned()](https://wg21.link/P1007R3) | 否 |
| &nbsp;&nbsp;[P1020R1 使用預設初始化的智慧型指標建立](https://wg21.link/P1020R1) | 否 |
| &nbsp;&nbsp;[P1023R0 constexpr 適用於 std::array 比較](https://wg21.link/P1023R0) | 否 |
| &nbsp;&nbsp;[P1032R1 其他 constexpr](https://wg21.link/P1032R1) | 否 |
| &nbsp;&nbsp;[P1165R1 basic_string 之 operator+() 中一致的傳播具狀態配置工具 ](https://wg21.link/P1165R1) | 否 |
| &nbsp;&nbsp;[P1285R0 改良型別特徵的完整性需求](https://wg21.link/P1285R0) | 否 |
| __C++17 標準庫功能__ | __支援__ |
| &nbsp;&nbsp;[LWG 2221 nullptr 的格式化輸出運算子](https://cplusplus.github.io/LWG/issue2221) | VS 2019 16.1 |
| &nbsp;&nbsp;[N3911 void_t](https://wg21.link/n3911) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4089 unique_ptr\<T[]> 中的安全轉換](https://wg21.link/n4089) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4169 invoke()](https://wg21.link/n4169) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4190 移除 auto_ptr、random_shuffle() 以及舊的 \<functional> 項目](https://wg21.link/n4190) | VS 2015 <sup>[rem](#note_rem)</sup> |
| &nbsp;&nbsp;[N4258 清除 noexcept](https://wg21.link/n4258) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4259 uncaught_exceptions()](https://wg21.link/n4259) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4277 完整可複製的 reference_wrapper](https://wg21.link/n4277) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4279 map/unordered_map 的 insert_or_assign()/try_emplace()](https://wg21.link/n4279) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4280 size()、empty()、data()](https://wg21.link/n4280) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4366 精確地限制 unique_ptr 指派](https://wg21.link/n4366) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4387 改善 pair 和 tuple](https://wg21.link/n4387) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4389 bool_constant](https://wg21.link/n4389) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4508 shared_mutex (Untimed)](https://wg21.link/n4508) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4510 vector/list/forward_list 中的不完整類型支援](https://wg21.link/n4510) | VS 2013 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4562 程式庫基本概念︰\<algorithm> sample()](https://wg21.link/n4562#alg.random.sample) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 程式庫基本概念︰\<any>](https://wg21.link/n4562#any) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 程式庫基本概念︰\<memory_resource>](https://wg21.link/n4562#memory.resource.synop)<br/>&nbsp;&nbsp;[P0337R0 刪除 polymorphic_allocator 指派](https://wg21.link/p0337r0) | VS 2017 15.6 |
| &nbsp;&nbsp;[N4562 程式庫基本概念︰\<optional>](https://wg21.link/n4562#optional) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 程式庫基本概念︰\<string_view>](https://wg21.link/n4562#string.view) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 程式庫基本概念︰\<tuple> apply()](https://wg21.link/n4562#tuple) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 程式庫基本概念︰Boyer-Moore search()](https://wg21.link/n4562#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 修正搜尋程式傳回型別](https://wg21.link/p0253r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0003R5 移除動態例外狀況規格](https://wg21.link/p0003r5) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0004R1 移除已取代的 Iostreams 別名](https://wg21.link/p0004r1) | VS 2015.2 <sup>[rem](#note_rem)</sup> |
| &nbsp;&nbsp;[P0005R4 not_fn()](https://wg21.link/p0005r4)<br/>&nbsp;&nbsp;[P0358R1 not_fn() 的修正](https://wg21.link/p0358r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0006R0 類型特性的變數範本 (is_same_v 等等)](https://wg21.link/p0006r0) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0007R1 as_const()](https://wg21.link/p0007r1) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0013R1 邏輯運算子類型特性 (conjunction 等等)](https://wg21.link/p0013r1) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0024R2 平行演算法](https://wg21.link/p0024r2)<br/>&nbsp;&nbsp;[P0336R1 重新命名平行執行原則](https://wg21.link/p0336r1)<br/>&nbsp;&nbsp;[P0394R4 針對例外狀況，平行演算法應使用 terminate()](https://wg21.link/p0394r4)<br/>&nbsp;&nbsp;[P0452R1 統一 \<numeric> 平行演算法](https://wg21.link/p0452r1) \(英文\) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0025R1 clamp()](https://wg21.link/p0025r1) | VS 2015.3 |
| &nbsp;&nbsp;[P0030R1 hypot(x, y, z)](https://wg21.link/p0030r1) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0031R0 \<array> (再次說明) 和 \<iterator> 的 constexpr](https://wg21.link/p0031r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0032R3 variant/any/optional 的同質性介面](https://wg21.link/p0032r3) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0033R1 改寫 enable_shared_from_this](https://wg21.link/p0033r1) | VS 2017 15.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0040R3 擴充記憶體管理工具](https://wg21.link/p0040r3) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0063R3 C11 標準程式庫](https://wg21.link/p0063r3) | VS 2015 <sup>[C11](#note_C11)、[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0067R5 基礎字串轉換](https://wg21.link/p0067r5) | VS 2019 16.4<sup>[字元](#note_charconv)</sup> |
| &nbsp;&nbsp;[P0074R0 owner_less\<>](https://wg21.link/p0074r0) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0077R2 is_callable、is_nothrow_callable](https://wg21.link/p0077r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0083R3 接合對應和集合](https://wg21.link/p0083r3)<br/>&nbsp;&nbsp;[P0508R0 釐清 insert_return_type](https://wg21.link/p0508r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0084R2 Emplace 傳回型別](https://wg21.link/p0084r2) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0088R3 \<variant>](https://wg21.link/p0088r3) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0092R1 \<chrono> floor()、ceil()、round()、abs()](https://wg21.link/p0092r1) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0152R1 atomic::is_always_lock_free](https://wg21.link/p0152r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size 等等](https://wg21.link/p0154r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0156R0 Variadic lock_guard](https://wg21.link/p0156r0) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0156R2 將 Variadic lock\_guard 重新命名為 scoped\_lock](https://wg21.link/p0156r2) \(英文\) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0163R0 shared_ptr::weak_type](https://wg21.link/p0163r0) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0174R2 取代不必要的程式庫組件](https://wg21.link/p0174r2) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0185R1 is_swappable、is_nothrow_swappable](https://wg21.link/p0185r1) | VS 2015.3 |
| &nbsp;&nbsp;[P0209R2 make_from_tuple()](https://wg21.link/p0209r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0218R1 \<filesystem>](https://wg21.link/p0218r1)<br/>&nbsp;&nbsp;[P0219R1 適用於 Filesystem 的相對路徑](https://wg21.link/p0219r1)<br/>&nbsp;&nbsp;[P0317R1 針對檔案系統的目錄項目快取](https://wg21.link/p0317r1) \(英文\)<br/>&nbsp;&nbsp;[P0392R0 支援 Filesystem 路徑的 string_view](https://wg21.link/p0392r0)<br/>&nbsp;&nbsp;[P0430R2 支援非 POSIX 檔案系統](https://wg21.link/p0430r2) \(英文\)<br/>&nbsp;&nbsp;[P0492R2 解決檔案系統的 NB 註解](https://wg21.link/p0492r2) \(英文\) | VS 2017 15.7 <sup>[E](#note_E)</sup> |
| &nbsp;&nbsp;[P0220R1 程式庫基本概念 V1](https://wg21.link/p0220r1) | VS 2017 15.6 |
| &nbsp;&nbsp;[P0226R1 數學特殊函式](https://wg21.link/p0226r1) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0254R2 整合 string_view 和 std::string](https://wg21.link/p0254r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0258R2 has_unique_object_representations](https://wg21.link/p0258r2) | VS 2017 15.3 <sup>[G](#note_G)</sup> |
| &nbsp;&nbsp;[P0272R1 非常數 basic_string::data()](https://wg21.link/p0272r1) | VS 2015.3 |
| &nbsp;&nbsp;[P0295R0 gcd()、lcm()](https://wg21.link/p0295r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0298R3 std::byte](https://wg21.link/p0298r3) \(英文\) | VS 2017 15.3 <sup>[17](#note_17)、&nbsp;[位元組](#note_byte)</sup> |
| &nbsp;&nbsp;[P0302R1 移除 std::function 中的配置器支援](https://wg21.link/p0302r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0307R2 再次說明如何使用 Optional >=](https://wg21.link/p0307r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0393R3 如何使用 Variant >=](https://wg21.link/p0393r3) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0403R1 適用於 \<string_view> ("meow"sv 等) 的 UDL](https://wg21.link/p0403r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0414R2 shared_ptr\<T[]>、shared_ptr\<T[N]>](https://wg21.link/p0414r2)<br/>&nbsp;&nbsp;[P0497R0 修正陣列的 shared_ptr](https://wg21.link/p0497r0) | VS 2017 15.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0418R2 不可部分完成的 compare_exchange memory_order 需求](https://wg21.link/p0418r2) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0426R1 char_traits 的 constexpr](https://wg21.link/p0426r1) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0433R2 將針對類別樣板的樣板推斷整合至標準程式庫](https://wg21.link/p0433r2) \(英文\)<br/>&nbsp;&nbsp;[P0739R0 改善針對標準程式庫的類別樣板引數推斷整合](https://wg21.link/p0739r0) \(英文\) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0435R1 檢修 common_type](https://wg21.link/p0435r1)<br/>&nbsp;&nbsp;[P0548R1 調校 common\_type 和 duration](https://wg21.link/p0548r1) \(英文\) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0504R0 重新認識 in_place_t/in_place_type_t\<T>/in_place_index_t\<I>](https://wg21.link/p0504r0) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0505R0 \<chrono> (再次說明) 的 constexpr](https://wg21.link/p0505r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0510R0 拒絕空白變異、陣列、參考和不完整類型](https://wg21.link/p0510r0) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0513R0 停用 hash](https://wg21.link/p0513r0)<br/>&nbsp;&nbsp;[P0599R1 noexcept 雜湊](https://wg21.link/p0599r1) \(英文\) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0516R0 將 shared_future 複製標記為 noexcept](https://wg21.link/p0516r0) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0517R0 從 future_errc 建構 future_error](https://wg21.link/p0517r0) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0521R0 取代 shared_ptr::unique()](https://wg21.link/p0521r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0558R1 解決不可部分完成\<T> 具名基底類別不一致](https://wg21.link/p0558r1) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0595R2 std::is_constant_evaluated()](https://wg21.link/P0595R2) | VS 2019 16.5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0602R4 在可變/選用中傳播複製/移動 Triviality](https://wg21.link/P0602R4) | VS 2017 15.3<sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0604R0 將 is\_callable/result\_of 變更為 invoke\_result、is\_invocable、is\_nothrow\_invocable](https://wg21.link/p0604r0) \(英文\) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0607R0 適用於標準程式庫的內嵌變數](https://wg21.link/p0607r0) \(英文\) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0618R0 取代 \<codecvt>](https://wg21.link/p0618r0) \(英文\) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0682R1 修復基礎字串轉換修復基礎字串轉換](https://wg21.link/P0682R1) | VS 2015 15.7 <sup>[17](#note_17)</sup> |
| __C++14 標準庫功能__ | __支援__ |
| &nbsp;&nbsp;[N3462 適合 SFINAE 的 result_of](https://wg21.link/n3462) | VS 2015.2 |
| &nbsp;&nbsp;[N3302 \<complex> 的 constexpr](https://wg21.link/n3302) | VS 2015 |
| &nbsp;&nbsp;[N3469 \<chrono> 的 constexpr](https://wg21.link/n3469) | VS 2015 |
| &nbsp;&nbsp;[N3470 \<array> 的 constexpr](https://wg21.link/n3470) | VS 2015 |
| &nbsp;&nbsp;[N3471 \<initializer_list>、\<tuple>、\<utility> 的 constexpr](https://wg21.link/n3471) | VS 2015 |
| &nbsp;&nbsp;[N3545 integral_constant::operator()()](https://wg21.link/n3545) | VS 2015 |
| &nbsp;&nbsp;[N3642 適用於 \<chrono>、\<string> 的 UDL (1729ms、"meow"s 等等)](https://wg21.link/n3642) | VS 2015 |
| &nbsp;&nbsp;[N3644 Null 正向迭代器](https://wg21.link/n3644) | VS 2015 |
| &nbsp;&nbsp;[N3654 quoted()](https://wg21.link/n3654) | VS 2015 |
| &nbsp;&nbsp;[N3657 異質關聯查閱](https://wg21.link/n3657) | VS 2015 |
| &nbsp;&nbsp;[N3658 integer_sequence](https://wg21.link/n3658) | VS 2015 |
| &nbsp;&nbsp;[N3659 shared_mutex (Timed)](https://wg21.link/n3659) | VS 2015 |
| &nbsp;&nbsp;[N3668 exchange()](https://wg21.link/n3668) | VS 2015 |
| &nbsp;&nbsp;[N3669 修正未含 const 的 constexpr 成員函式](https://wg21.link/n3669) | VS 2015 |
| &nbsp;&nbsp;[N3670 get\<T>()](https://wg21.link/n3670) | VS 2015 |
| &nbsp;&nbsp;[N3671 雙重範圍 equal()、is_permutation()、mismatch()](https://wg21.link/n3671) | VS 2015 |
| &nbsp;&nbsp;[N3778 依大小調整的解除配置](https://wg21.link/n3778) | VS 2015 |
| &nbsp;&nbsp;[N3779 適用於 \<complex> 的 UDL (3.14i 等等)](https://wg21.link/n3779) | VS 2015 |
| &nbsp;&nbsp;[N3789 \<functional> 的 constexpr](https://wg21.link/n3789) | VS 2015 |
| &nbsp;&nbsp;[N3887 tuple_element_t](https://wg21.link/n3887) | VS 2015 |
| &nbsp;&nbsp;[N3891 重新命名 shared_mutex (Timed) 為 shared_timed_mutex](https://wg21.link/n3891) | VS 2015 |
| &nbsp;&nbsp;[N3346 容器元素的最低需求](https://wg21.link/n3346) | VS 2013 |
| &nbsp;&nbsp;[N3421 透明運算子函式 (less\<> 等等)](https://wg21.link/n3421) | VS 2013 |
| &nbsp;&nbsp;[N3655 適用於 \<type_traits> 的別名範本 (decay_t 等等)](https://wg21.link/n3655) | VS 2013 |
| &nbsp;&nbsp;[N3656 make_unique()](https://wg21.link/n3656) | VS 2013 |

一組一起列出的檔表示標準功能以及一個或多個已批准的改進或擴展。 這些功能皆會一起實作。

### <a name="supported-values"></a>支援的值

__沒有__尚未實現的方法。
「部分」____ 表示實作不完整。 有關詳細資訊,請參閱註釋部分。
__VS 2010__表示 Visual Studio 2010 中支援的功能。
__VS 2013__表示 Visual Studio 2013 中支援的功能。
__VS 2015__表示 Visual Studio 2015 (RTW) 中支援的功能。
__VS 2015.2__和__VS 2015.3__分別表示 Visual Studio 2015 更新 2 和 Visual Studio 2015 更新 3 中支援的功能。
__VS 2017 15.0__表示 Visual Studio 2017 版本 15.0 (RTW) 中支援的功能。
__VS 2017 15.3__表示 Visual Studio 2017 版本 15.3 版中支援的功能。
__VS 2017 15.5__表示 Visual Studio 2017 版本 15.5 中支援的功能。
__VS 2017 15.7__表示 Visual Studio 2017 版本 15.7 中支援的功能。
__VS 2019 16.0__表示 Visual Studio 2019 版本 16.0 (RTW) 中支援的功能。
__VS 2019 16.1__表示 Visual Studio 2019 版本 16.1 版中支援的功能。
__VS 2019 16.2__表示 Visual Studio 2019 版本 16.2 版中支援的功能。
__VS 2019 16.3__表示 Visual Studio 2019 版本 16.3 版中支援的功能。
__VS 2019 16.4__表示 Visual Studio 2019 版本 16.4 版中支援的功能。
__VS 2019 16.5__表示 Visual Studio 2019 版本 16.5 中支援的功能。

### <a name="notes"></a>注意

<a name="note_A"></a> __A__ 在 [/std:c++14](../build/reference/std-specify-language-standard-version.md) 模式中，動態例外狀況規格保持未實作，而 `throw()` 仍被視為 `__declspec(nothrow)` 的同義字。 在 C++17 中，P0003R5 移除了大部分的動態例外狀況規格，並保留一個殘留項目：`throw()` 將會被淘汰，而且必須作為 `noexcept` 的同義字。 在[/std:c++17](../build/reference/std-specify-language-standard-version.md)模式下,MSVC`throw()`現在`noexcept`通過提供 與 相同的行為(即通過終止強制執行)來符合標準。

編譯器選項 [/Zc:noexceptTypes](../build/reference/zc-noexcepttypes.md) 會要求 `__declspec(nothrow)` 的舊行為。 很可能在`throw()`C++20 中刪除。 為了協助移轉程式碼以回應標準及我們實作中的這些變更，已在 [/std:c++17](../build/reference/std-specify-language-standard-version.md) 和 [/permissive-](../build/reference/permissive-standards-conformance.md) 下新增例外狀況規格問題的編譯器警告。

<a name="note_B"></a>__B__在 Visual Studio 2017 版 15.7 中支援[/允許模式](../build/reference/permissive-standards-conformance.md)。 有關詳細資訊,請參閱[MSVC 上提供兩階段名稱尋找支援](https://devblogs.microsoft.com/cppblog/two-phase-name-lookup-support-comes-to-msvc/)。

<a name="note_C"></a>__C__在 Visual Studio 2017 中,編譯器對 C99 預處理器規則的支援不完整。 我們正在對預處理器進行大修,並開始在 Visual Studio 2017 版 15.8 中使用[/實驗:前處理器](../build/reference/experimental-preprocessor.md)編譯器開關提供這些更改。

<a name="note_D"></a> __D__ 於 [/std:c++14](../build/reference/std-specify-language-standard-version.md) 底下受到支援，並具有可隱藏的警告，[C4984](../error-messages/compiler-warnings/compiler-warning-c4984.md)。

<a name="note_E"></a>__E__這是一個全新的實現,與以前`std::experimental`的 版本不相容,通過 symlink 支援、錯誤修復和標準要求行為的更改而是必需的。 目前，包括 \<filesystem>可提供新的 `std::experimental::filesystem` 和之前的 \<，而包括 `std::filesystem`experimental/filesystem> 只會提供舊的實驗性實作。 實驗性實作將會在程式庫的下一個 ABI 重大版本中「移除」。

<a name="note_G"></a> __G__ 由編譯器內建支援。

<a name="note_14"></a> __14__ 這些 C++17/20 功能一律會啟用，就算在指定 [/std:c++14](../build/reference/std-specify-language-standard-version.md) (預設值) 的情況下也一樣。 原因是因為功能是在**引入 /std**選項之前實現的,要麼是因為條件實現異常複雜。

<a name="note_17"></a> __17__ 這些功能是由 [/std:c++17](../build/reference/std-specify-language-standard-version.md) (或 [/std:c++latest](../build/reference/std-specify-language-standard-version.md)) 編譯器選項啟用。

<a name="note_20"></a> __20__ 這些功能是由 [/std:c++latest](../build/reference/std-specify-language-standard-version.md) 編譯器選項啟用。 當 C++20 實作完成時，將會新增 **/std:c++20** 編譯器選項，這些功能將在該選項下可供使用。

<a name="note_byte"></a> __byte__ `std::byte` 是由 [/std:c++17](../build/reference/std-specify-language-standard-version.md) (或 [/std:c++latest](../build/reference/std-specify-language-standard-version.md)) 啟用，但它在某些情況下可能會與 Windows SDK 標頭發生衝突，並具有可微調的退出巨集。 可以透過將 `_HAS_STD_BYTE` 定義為 `0`來停用它。

<a name="note_C11"></a> __C11__ 通用 CRT 已實作 C++17 所需的 C11 標準程式庫組件，除了 C99 `strftime()` E/O 替代轉換規範、C11 `fopen()` 獨佔模式，以及 C11 `aligned_alloc()`之外。 後者不太可能實現,因為 C11`aligned_alloc()`的指定`free()`方式與 Microsoft`free()`實現不相容, 即必須能夠處理高度一致的分配。

<a name="note_rem"></a> __rem__ 當指定 [/std:c++17](../build/reference/std-specify-language-standard-version.md) (或 [/std:c++latest](../build/reference/std-specify-language-standard-version.md)) 編譯器選項時，將會移除這些功能。 您可以使用下列巨集重新啟用這些功能以清除轉換到新語言模式：`_HAS_AUTO_PTR_ETC`、`_HAS_FUNCTION_ALLOCATOR_SUPPORT`、`_HAS_OLD_IOSTREAMS_MEMBERS` 與 `_HAS_UNEXPECTED`。

<a name="note_charconv"></a> __charconv__ `from_chars()` 與 `to_chars()` 可用於整數。 浮點數 `from_chars()` 與浮點數 `to_chars()` 的時間表如下所示：

- VS 2017 15.7:`from_chars()`整`to_chars()`數和 。
- VS 2017 15.8:`from_chars()`浮點 .
- VS 2017 15.9:短`to_chars()`小數的浮點過載。
- VS 2019 16.0:浮`to_chars()`點過載,用於最短的六角和精密十六進制。
- VS 2019 16.2:浮`to_chars()`點過載,實現精確固定和精確科學。
- VS 2019 16.4:`to_chars()`精度 一般浮點過載。

<a name ="note_parallel"></a>__並行__C++17 的並行演演演算法庫已完成。 完成並不意味著每個演演演算法在每種情況下都並行化。 最重要的演演演算法已並行化,即使演演演算法未並行化,也會提供執行策略簽名。 我們的實現的核心內部標頭 yvals_core.h 包含以下"並行演演演算法註釋":C++允許實現作為對串列演演演算法的調用實現並行演演演算法。 這項實作會平行處理數個常見的演算法呼叫，但並非全部。

下列演算法已平行處理：

- `adjacent_difference`, `adjacent_find`, `all_of`, `any_of`, `count`, `count_if`, `equal`, `exclusive_scan`, `find`, `find_end`, `find_first_of`, `find_if`, `find_if_not`, `for_each`, `for_each_n`, `inclusive_scan`, `is_heap`, `is_heap_until`, `is_partitioned`, `is_sorted`, `is_sorted_until`, `mismatch`, `none_of`, `partition`, `reduce`, `remove`, `remove_if`, `replace`, `replace_if`, `search`, `search_n`, `set_difference`, `set_intersection`, `sort`, `stable_sort`, `transform`, `transform_exclusive_scan`, `transform_inclusive_scan`, `transform_reduce`

以下部份目前未行化:

- 目標硬體上沒有明顯的並行性能改進;所有僅複製或滲透沒有分支的元素的演算法通常記憶體頻寬受限:
  - `copy`, `copy_n`, `fill`, `fill_n`, `move`, `reverse`, `reverse_copy`, `rotate`, `rotate_copy`, `shift_left`, `shift_right`, `swap_ranges`
- 使用者平行處理原則的需求存在混淆。仍可能在上述類別目錄中：
  - `generate`, `generate_n`
- 有效的平行處理可能不可行：
  - `partial_sort`, `partial_sort_copy`
- 尚未評估；平行處理也許會在未來版本中實作，而且可能有幫助：
  - `copy_if`, `includes`, `inplace_merge`, `lexicographical_compare`, `max_element`, `merge`, `min_element`, `minmax_element`, `nth_element`, `partition_copy`, `remove_copy`, `remove_copy_if`, `replace_copy`, `replace_copy_if`, `set_symmetric_difference`, `set_union`, `stable_partition`, `unique`, `unique_copy`

## <a name="see-also"></a>另請參閱

[C++語言參考](../cpp/cpp-language-reference.md)\
[C++標準庫](../standard-library/cpp-standard-library-reference.md)\
[視覺工作室C++一致性改進](cpp-conformance-improvements.md)\
[視覺工作室中視覺C++的新增功能](what-s-new-for-visual-cpp-in-visual-studio.md)\
[視覺C++ 2003 年至 2015 年更改歷史記錄](../porting/visual-cpp-change-history-2003-2015.md)\
[視覺C++ 2003 年至 2015 年的新增功能](../porting/visual-cpp-what-s-new-2003-through-2015.md)\
[C++ 小組部落格](https://devblogs.microsoft.com/cppblog/)
