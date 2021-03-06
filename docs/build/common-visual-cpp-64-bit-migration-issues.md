---
title: Visual C++ 64 位元移轉時常見的問題
ms.date: 05/06/2019
helpviewer_keywords:
- 64-bit programming [C++], migration
- 64-bit compiler [C++], migration
- porting 32-bit code to 64-bit code
- migration [C++], 64-bit code issues
- 32-bit code porting [C++]
- 64-bit applications [C++]
- 64-bit compiler [C++], porting 32-bit code
- Win64 [C++]
ms.assetid: d17fb838-7513-4e2d-8b27-a1666f17ad76
ms.openlocfilehash: 004fe7ace6102feecbcb2f542b5b93268ae2f868
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493318"
---
# <a name="common-visual-c-64-bit-migration-issues"></a>Visual C++ 64 位元移轉時常見的問題

當您使用 Microsoft c + + 編譯器（MSVC）來建立要在64位 Windows 作業系統上執行的應用程式時，您應該注意下列問題：

- `int` 和 `long` 是 64 位元 Windows 作業系統上的 32 位元值。 對於您要為 64 位元平台進行編譯的程式，您應小心不要將指標指派給 32 位元變數。 指標在 64 位元平台上是 64 位元的，如果您將指標指派給 32 位元變數，將會截斷指標值。

- `size_t`、 `time_t`和`ptrdiff_t`是64位 Windows 作業系統上的64位值。

- `time_t`在 Visual Studio 2005 和更早版本中，在32位 Windows 作業系統上是32位的值。 `time_t` 現在預設為 64 位元整數。 如需詳細資訊，請參閱[時間管理](../c-runtime-library/time-management.md)。

   您應注意程式碼在何處取用 `int` 值，並將其視為 `size_t` 或 `time_t` 值來處理。 此數值可能會成長而大於 32 位元數值，且資料在傳回至 `int` 儲存體時將會截斷。

%x (十六進位 `int` 格式) `printf` 修飾詞在 64 位元 Windows 作業系統上將無法如預期運作。 它只會處理傳遞給它之值的前 32 個位元。

- 使用 %I32x 可顯示十六進位格式的 32 位元整數類型。

- 使用 %I64x 顯示十六進位格式的 64 位元整數類型。

- %p (指標的十六進位格式) 在 64 位元 Windows 作業系統上將如預期運作。

如需詳細資訊，請參閱

- [MSVC 編譯器選項](reference/compiler-options.md)

- [移轉提示](/windows/win32/WinProg64/migration-tips)

## <a name="see-also"></a>請參閱

[設定適用於 64 位元、x64 目標的 C++ 專案](configuring-programs-for-64-bit-visual-cpp.md)<br/>
[Visual C++ 移植和升級指南](../porting/visual-cpp-porting-and-upgrading-guide.md)
