---
title: 編譯器警告 （層級 1） C4047
ms.date: 11/04/2016
f1_keywords:
- C4047
helpviewer_keywords:
- C4047
ms.assetid: b75ad6fb-5c93-4434-a85f-c4083051a5de
ms.openlocfilehash: 87c9e39e5dac40341adc63af45cc0e460806c736
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666501"
---
# <a name="compiler-warning-level-1-c4047"></a>編譯器警告 （層級 1） C4047

'operator' : 'identifier1' 在間接層級中不同於 'identifier2'

指標可以指向的變數 （一層間接取值），另一個指標指向變數 （兩層間接取值），依此類推。

## <a name="example"></a>範例

下列範例會產生 C4047:

```
// C4047.c
// compile with: /W1

int main() {
   char **p = 0;   // two levels of indirection
   char *q = 0;   // one level of indirection

   char *p2 = 0;   // one level of indirection
   char *q2 = 0;   // one level of indirection

   p = q;   // C4047
   p2 = q2;
}
```

## <a name="example"></a>範例

下列範例會產生 C4047:

```
// C4047b.c
// compile with: /W1
#include <stdio.h>

int main() {
   int i;
   FILE *myFile = NULL;
   errno_t  err = 0;
   char file_name[256];
   char *cs = 0;

   err = fopen_s(&myFile, "C4047.txt", "r");
   if ((err != 0) || (myFile)) {
      printf_s("fopen_s failed!\n");
      exit(-1);
    }
   i = fgets(file_name, 256, myFile);   // C4047
   cs = fgets(file_name, 256, myFile);   // OK
}
```