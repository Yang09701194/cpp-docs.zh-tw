---
title: FileOutput 類別
description: C++ BUILD Insights SDK FileOutput 類別參考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1c4053d0378ddb9d5dd061bbc9889c454dc9b52c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333339"
---
# <a name="fileoutput-class"></a>FileOutput 類別

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK 與 Visual Studio 2017 和更新版本相容。 若要查看這些版本的檔，請將本文的 Visual Studio 版本選取器控制項設定為 Visual Studio 2017 或 Visual Studio 2019。

::: moniker-end
::: moniker range=">=vs-2017"

`FileOutput` 類別會與[MatchEvent](../functions/match-event.md)、 [MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、 [MatchEventStack](../functions/match-event-stack.md)和[MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md)函數搭配使用。 使用它來比對[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output)、 [EXP_OUTPUT](../event-table.md#exp-output)、 [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output)、 [LIB_OUTPUT](../event-table.md#lib-output)或[OBJ_OUTPUT](../event-table.md#obj-output)事件。

## <a name="syntax"></a>語法

```cpp
class FileOutput : public SimpleEvent
{
public:
    enum class Type
    {
        OTHER               = FILE_TYPE_CODE_OTHER,
        OBJ                 = FILE_TYPE_CODE_OBJ,
        EXECUTABLE_IMAGE    = FILE_TYPE_CODE_EXECUTABLE_IMAGE,
        LIB                 = FILE_TYPE_CODE_LIB,
        IMP_LIB             = FILE_TYPE_CODE_IMP_LIB,
        EXP                 = FILE_TYPE_CODE_EXP
    };

    FileOutput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>成員

除了來自其[SimpleEvent](simple-event.md)基類的繼承成員之外，`FileOutput` 類別還包含下列成員：

### <a name="constructors"></a>建構函式

[FileOutput](#file-output)

### <a name="functions"></a>Functions

[路徑](#path)
[類型](#type)

## <a name="file-output"></a>FileOutput

```cpp
FileOutput(const RawEvent& event);
```

### <a name="parameters"></a>參數

*event*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output)、 [EXP_OUTPUT](../event-table.md#exp-output)、 [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output)、 [LIB_OUTPUT](../event-table.md#lib-output)或[OBJ_OUTPUT](../event-table.md#obj-output)事件。

## <a name="path"></a> Path

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>傳回值

輸出檔的絕對路徑。

## <a name="type"></a>型

```cpp
Type Type() const;
```

### <a name="return-value"></a>傳回值

描述輸出檔類型的程式碼。

::: moniker-end