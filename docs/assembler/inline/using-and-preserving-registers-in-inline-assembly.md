---
title: 在內嵌組譯碼中使用和保留暫存器
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], register values
- inline assembly, registers
- registers, inline assembly
- preserving registers
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
ms.openlocfilehash: 97db09ac7652c00e9599a6938f4114de080906c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318033"
---
# <a name="using-and-preserving-registers-in-inline-assembly"></a>在內嵌組譯碼中使用和保留暫存器

**Microsoft 特定的**

一般而言，您不應該假設暫存器會在 `__asm` 區塊開始時有指定值。 不保證跨不同的 `__asm` 區塊會保留暫存器值。 如果您結束內嵌程式碼區塊並開始另一個區塊，您就不能依賴第二個區塊中的暫存器從第一個區塊保有其值。 `__asm` 區塊會繼承一般控制流程所產生的任何暫存器值。

如果使用 `__fastcall` 呼叫慣例，編譯器會傳遞暫存器中的函式引數，而非堆疊上的函式引數。 這可能會在包含 `__asm` 區塊的函式中引起問題，因為函式無法判斷哪一個參數在哪一個暫存器中。 如果函式剛好在 EAX 中接收參數並立即將其他參數儲存在 EAX 中，則會失去原始參數。 此外，您必須將 ECX 暫存器保留在任何以 `__fastcall` 宣告的函式中。

為避免這種暫存器衝突，請勿將 `__fastcall` 慣例用於包含 `__asm` 區塊的函式。 如果使用 /Gr 編譯器選項全域指定 `__fastcall` 慣例，請以 `__asm` 或 `__cdecl` 宣告每一個包含 `__stdcall` 區塊的函式  (該`__cdecl`屬性告訴編譯器對該函數使用 C 調用約定。如果不使用 /Gr 編譯,請避免使用 屬性`__fastcall`宣告函數 。

當使用 `__asm` 在 C/C++ 函式中寫入組合語言時，您不需要保留 EAX、EBX、ECX 和 EDX、ESI 或 EDI 暫存器。 例如,在 POWER2 中。C 在[使用內聯程式集寫入函數](../../assembler/inline/writing-functions-with-inline-assembly.md)`power2`中的範例 ,該函數不保留 EAX 寄存器中的值。 不過，因為暫存器配置器不能利用這些暫存器跨 `__asm` 區塊儲存值，因此使用這些暫存器會影響程式碼品質。 此外，您可以在內嵌組譯碼中使用 EBX、ESI 或 EDI 來強制編譯器在函式序言和結尾中儲存及還原這些暫存器。

您應該保留用於 `__asm` 區塊範圍的其他暫存器 (例如 DS、SS、SP、BP 和旗標暫存器)。 除非您有需要變更的理由 (例如切換堆疊)，否則您應該保留 ESP 和 EBP 暫存器。 另請參閱[最佳化內聯程式集](../../assembler/inline/optimizing-inline-assembly.md)。

部分 SSE 類型需要有八個位元組的堆疊對齊，強制編譯器發出動態堆疊對齊程式碼。 為了在對齊後能夠存取區域變數和函式參數二者，編譯器會保留兩個框架指標。  如果編譯器執行幀指標遺漏 (FPO),它將使用 EBP 和 ESP。  如果編譯器不執行 FPO,它將使用 EBX 和 EBP。 為確保程式碼能夠正確執行，如果函式為了能夠修改框架指標而需要動態堆疊對齊，請勿修改 asm 程式碼中的 EBX。 您可以將八位元組的對齊類型移到函式以外，或者避免使用 EBX。

> [!NOTE]
> 如果內嵌組譯碼使用 STD 或 CLD 指令變更方向旗標，您必須將旗標還原為其原始值。

**結束微軟的**

## <a name="see-also"></a>另請參閱

[內嵌組合語言](../../assembler/inline/inline-assembler.md)<br/>
