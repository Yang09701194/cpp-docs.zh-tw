---
title: 跳至內嵌組譯碼中的標籤
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembly, jumping to labels
- labels, in inline assembly
- __asm keyword [C++], labels
- case sensitivity, labels in inline assembly
- labels, in __asm blocks
- jumping to labels in inline assembly
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
ms.openlocfilehash: 199156a08af13f4a70793609b37c70b0c95bf9ba
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169327"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>跳至內嵌組譯碼中的標籤

**Microsoft 專屬**

`__asm` 區塊中的標籤就像一般 C 或 C++ 標籤，擁有的範圍涵蓋本身定義所在的整個函式 (而不只是區塊)。 組件指令和 `goto` 陳述式都可以跳至 `__asm` 區塊內部或外部的標籤。

在 `__asm` 區塊中定義的標籤不區分大小寫，`goto` 陳述式和組件指令都可以參考這些標籤，而不需考慮大小寫。 C 和 C++ 標籤只有在 `goto` 陳述式使用時才區分大小寫。 組件指令可以跳至 C 或 C++ 標籤，而不需考慮大小寫。

下列程式碼將顯示所有排列：

```cpp
void func( void )
{
   goto C_Dest;  /* Legal: correct case   */
   goto c_dest;  /* Error: incorrect case */

   goto A_Dest;  /* Legal: correct case   */
   goto a_dest;  /* Legal: incorrect case */

   __asm
   {
      jmp C_Dest ; Legal: correct case
      jmp c_dest ; Legal: incorrect case

      jmp A_Dest ; Legal: correct case
      jmp a_dest ; Legal: incorrect case

      a_dest:    ; __asm label
   }

   C_Dest:       /* C label */
   return;
}
int main()
{
}
```

不要使用 C 程式庫函式名稱做為 `__asm` 區塊中的標籤。 例如，下列情況可能會讓您想要使用 `exit` 做為標籤：

```cpp
; BAD TECHNIQUE: using library function name as label
   jne exit
   .
   .
   .
exit:
   ; More __asm code follows
```

由於**exit**是 C 程式庫函式的名稱，因此這個程式碼可能會導致跳至**exit**函式，而不是所需的位置。

如同在 MASM 程式中，貨幣符號 (`$`) 會做為目前位置計數器。 它是目前所組合之指示的標籤。 在 `__asm` 區塊中，其主要用途是提供長的條件式跳躍點：

```cpp
   jne $+5 ; next instruction is 5 bytes long
   jmp farlabel ; $+5
   .
   .
   .
farlabel:
```

**END Microsoft 特定的**

## <a name="see-also"></a>另請參閱

[內嵌組合語言](../../assembler/inline/inline-assembler.md)<br/>
