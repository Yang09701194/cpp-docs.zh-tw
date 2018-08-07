---
title: 如何： 宣告及使用內部指標和 Managed 的陣列 (C + + /cli CLI) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pointers, interior
- arrays [C++], managed
ms.assetid: e61a2c09-a7d0-4867-91ea-6b8788a01079
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c02849bc3d1b45ecb6de89e103c51311af31b3c
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569839"
---
# <a name="how-to-declare-and-use-interior-pointers-and-managed-arrays-ccli"></a>如何：宣告及使用內部指標和 Managed 陣列 (C++/CLI)
下列 C + + /cli CLI 範例會示範如何宣告和使用內部指標陣列。  
  
> [!IMPORTANT]
>  `/clr` 編譯器選項支援這項語言功能，`/ZW` 編譯器選項則不支援。  
  
## <a name="example"></a>範例  
  
### <a name="code"></a>程式碼  
  
```cpp  
// interior_ptr_arrays.cpp  
// compile with: /clr  
#define SIZE 10  
  
int main() {  
   // declare the array  
   array<int>^ arr = gcnew array<int>(SIZE);  
  
   // initialize the array  
   for (int i = 0 ; i < SIZE ; i++)  
      arr[i] = i + 1;  
  
   // create an interior pointer into the array  
   interior_ptr<int> ipi = &arr[0];  
  
   System::Console::WriteLine("1st element in arr holds: {0}", arr[0]);  
   System::Console::WriteLine("ipi points to memory address whose value is: {0}", *ipi);  
  
   ipi++;  
   System::Console::WriteLine("after incrementing ipi, it points to memory address whose value is: {0}", *ipi);  
}  
```  
  
### <a name="output"></a>輸出  
  
```Output  
1st element in arr holds: 1  
ipi points to memory address whose value is: 1  
after incrementing ipi, it points to memory address whose value is: 2  
```  
  
## <a name="see-also"></a>另請參閱  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)