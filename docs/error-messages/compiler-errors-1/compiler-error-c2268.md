---
title: 編譯器錯誤 C2268 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2268
dev_langs:
- C++
helpviewer_keywords:
- C2268
ms.assetid: 0ed055c9-3c6f-4df2-a5b6-85cf0e01a249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a38269cbd3bf133841e42a4197e986deb3167ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2268"></a>編譯器錯誤 C2268
'function' 是編譯器預先定義的程式庫 Helper。 /GL 不支援程式庫 Helper，請不要使用 /GL 來編譯目的檔 'file' 。  
  
 原始程式碼中所定義的函式與內部編譯器函式同名。 在沒有 [/GL](../../build/reference/gl-whole-program-optimization.md)的情況下，編譯包含函式的模組。  
  
 下列範例會產生 C2268：  
  
```  
// C2268.c  
// compile with: /c  
// processor: x86  
extern int SHFusionLoadLibrary(int lpLibFileName);  
  
int __cdecl _except_handler3(void) {  
   return SHFusionLoadLibrary(0);  
}  
  
extern int main(void);  
  
void* mainCRTStartup(void* p) {  
   p = main;  
   return p;  
}  
```  
  
 然後：  
  
```  
// C2268b.c  
// compile with: C2268.c /EHsc /GL /Ob0 /O2 /Fa /GS- /link /nodefaultlib  
// processor: x86  
extern int SHFusionLoadLibrary(int lpLibFileName);  
  
extern int __cdecl _except_handler3(void);  
extern void mainCRTStartup(void*);  
int g = 2;  
  
#define ENTERCONTEXT(fail) \  
   int ulCookie = 0;\  
   if (!SHActivateContext(&ulCookie)) \  
      return fail;\  
   __try {  
  
#define LEAVECONTEXT \  
    } __finally {SHDeactivateContext(ulCookie);}  
  
int SHActivateContext(int* a) {  
    return *a == g || !*a ||_except_handler3();  
}  
  
void SHDeactivateContext(int a) {  
    g = a;  
}  
  
int SHFusionLoadLibrary(int lpLibFileName) {   // C2268  
    ENTERCONTEXT(0)  
    g = lpLibFileName;  
    LEAVECONTEXT  
  
    return lpLibFileName;  
}  
  
int main(void) {  
    g = SHFusionLoadLibrary(10);  
    return 0;  
}  
```