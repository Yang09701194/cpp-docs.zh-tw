# <a name="contributing"></a>貢獻

感謝您對貢獻到 Visual C++ 文件有興趣！

本主題中，您可看到在 [Visual C++ 文件網站](https://docs.microsoft.com/cpp)中新增或更新內容的基本程序。

本主題將會探討：

* [投稿程序](#process-for-contributing)
* [使用規範](#dos-and-donts)
* [建置文件](#building-the-docs)
* [提供範例](#contributing-to-samples)
* [參與者授權合約](#contributor-license-agreement)

## <a name="process-for-contributing"></a>投稿程序

**步驟 1：** 建立一項議題，描述您希望撰寫的文章，及該文章與現有內容的相關性如何。
**docs** 資料夾中的內容，依內容領域 (例如，偵錯工具) 整理為章節。 請嘗試為您新的內容判斷正確的資料夾。 取得您提案的意見反應。

若為小量變更，可略過此第一步驟。

**步驟 2：** 派生 `MicrosoftDocs/cpp-docs` 存放庫。

**步驟 3：** 為您的文章建立 `branch`。

**步驟 4：** 撰寫文章。

若此為新主題，您可使用這個[範本檔案](./styleguide/template.md)作為起點。 其包含撰寫指導方針，同時也會說明每篇文章所需的中繼資料，例如作者資訊。

請瀏覽至對應到步驟 1 中為您文章所決定的目錄位置資料夾。
該資料夾包含該章節中所有文章的 Markdown 檔案。 請視需要建立新的資料夾，以存放您內容的檔案。

如需影像及其他靜態資源，請將其新增至名為 `media` 的子資料夾。 若目前正在為內容建立新的資料夾，請將媒體資料夾加入新的資料夾。

請務必遵循正確的 Markdown 語法。 如需詳細資訊，請參閱[樣式指南](./styleguide/template.md)。

### <a name="example-structure"></a>範例結構

    docs
        /standard-library
            wstring-convert-class.md
            /media
                wstring-conversion.png

**步驟 5：** 從您的分支將提取要求 (PR) 提交至 `MicrosoftDocs/cpp-docs/master`。

若您的 PR 可解決現有的問題，請對認可訊息或 PR 描述新增 `Fixes #Issue_Number` 關鍵字，該問題即可於合併 PR 時，自動解決。 如需詳細資訊，請參閱[經由認可訊息結束問題](https://help.github.com/articles/closing-issues-via-commit-messages/)。

Visual Studio 小組會檢閱您的 PR，並會讓您知道變更是否適合，或是否需要任何其他更新/變更，才能核准。

**步驟 6：** 和小組討論後，對分支進行所有必要的更新。

進行過意見反應的更動，且您的變更也適切之後，維護人員即會將您的 PR 合併到主要分支。

我們會依特定的頻率，將所有認可項目從主分支推送到即時分支，如此就可以即時於 [docs.microsoft.com](https://docs.microsoft.com/cpp/) 看到您貢獻的內容。

## <a name="dos-and-donts"></a>可進行及不可進行的事項

以下是一份您投稿 .NET 文件時，應謹記在心的指導規則清單。

- 請**不要**提交大量提取要求，讓我們措手不及。 而是請您先提出問題並開始討論，我們會在您投入大量的時間之前，先行確認方向。
- **請務必**閱讀[樣式指南](./styleguide/template.md)與[語態和語氣](./styleguide/voice-tone.md)指導方針。
- **請務必**使用[範本](./styleguide/template.md)檔案作為您開始工作的起點。
- **請務必**在對文章進行作業之前，先在分叉上建立您自己的分支。
- **請務必**遵循 [GitHub 流程的工作流程](https://guides.github.com/introduction/flow/)。
- **請務必**利用部落格及推特 (或任何其他形式)，頻繁地發表您的文章！

> [!NOTE]
> 您可能注意到有部份的主題未完全遵循此處所指定的指導方針，以及[樣式指南](./styleguide/template.md)。 我們目前正在努力達到整個網站的一致性。 請查看我們目前正致力於達到特定目標的[未解問題](https://github.com/MicrosoftDocs/cpp-docs/issues?q=is%3Aissue+is%3Aopen+label%3Aguidelines-adherence)清單。

## <a name="building-the-docs"></a>建置文件

文件以 [GitHub Flavored Markdown](https://help.github.com/categories/writing-on-github/) 撰寫，且使用 [DocFX](https://dotnet.github.io/docfx/) 及其他內部發行/建置工具所建置。 裝載於 [docs.microsoft.com](https://docs.microsoft.com/)。

若希望於本機建置文件，必須先安裝 [DocFX](https://dotnet.github.io/docfx/) (最新版本為最佳)。

有數種方法可使用 DocFX，而大部分都涵蓋在 [DocFX 入門指南](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html)內。 以下指示使用工具的[命令列](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html#2-use-docfx-as-a-command-line-tool)版本。 若您習慣利用上方連結所列的其他方式，可自由使用那些方式。

**注意：** DocFX 目前需要 .NET Framework (Windows) 或 Mono (Linux 或 macOS)。 希望未來能移植到 .NET Core。

您可使用內建網頁伺服器，於本機建置及預覽所產生的網站。 請巡覽至您電腦的 `cpp-docs\docs` 資料夾，然後鍵入下列命令：

> docfx -t default --serve

如此即可於 [localhost:8080](http://localhost:8080) 上啟動本機預覽。 接著即可前往 `http://localhost:8080/[path]` 檢視變更，例如 `http://localhost:8080/cpp/visual-cpp-in-visual-studio.html`。

**注意：** 本機預覽目前不包含任何佈景主題，所以風格及外觀不會與文件網站中的相同。 我們正努力修正這樣的體驗。 我們也為內嵌影片、備註和內含文件使用了一些自訂延伸模組，而這些並不會在預覽中出現。

## <a name="contributing-to-samples"></a>提供範例

現在，請先在您文章中將必要的範例程式碼，納入為內嵌程式碼區塊。 此存放庫有 `codesnippets` 資料夾，但尚未準備好用於公開貢獻。

## <a name="contributor-license-agreement"></a>參與者授權合約

您必須在合併 PR 前，先簽署[貢獻授權合約 (CLA)](LICENSE)。 docs.microsoft.com 中專案的只會提出一次這項要求。 您可於 Wikipedia 上閱讀更多關於[貢獻授權合約 (CLA)](https://en.wikipedia.org/wiki/Contributor_License_Agreement) 的資訊。

您不必預先簽署合約。 您可以一如往常地複製、派生和提交 PR。 PR 建立後，CLA Bot 就會為其分類。 如果是無關緊要的變更 (例如修正錯字)，PR 就會加上不需要 CLA 的標籤。 否則，就會分類為需要 CLA。 只要您簽署了 CLA，目前及日後的所有提取要求就都會標記為已簽署 CLA。
