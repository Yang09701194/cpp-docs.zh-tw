---
title: 編譯器錯誤 C3399 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3399
dev_langs:
- C++
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f694f9461c923d70040370819eaca6a18568c99b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3399"></a>編譯器錯誤 C3399
'type': 建立泛型參數的執行個體時無法提供引數  
  
 當您指定 `gcnew()` 條件約束時，即指定了無參數建構函式的條件約束類型。 因此，它是嘗試具現化該類型並傳遞參數的錯誤。  
  
 請參閱[泛型型別參數的條件約束 (C + + /CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)如需詳細資訊。  
  
## <a name="example"></a>範例  
 下列範例會產生 C3399。  
  
```  
// C3399.cpp  
// compile with: /clr /c  
generic <class T>   
where T : gcnew()  
void f() {  
   T t = gcnew T(1);   // C3399  
   T t2 = gcnew T();   // OK  
}  
```