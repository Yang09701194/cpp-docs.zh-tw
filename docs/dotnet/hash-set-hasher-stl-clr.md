---
title: "hash_set::hasher (STL/CLR) |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_set::hasher
dev_langs: C++
helpviewer_keywords: hasher member [STL/CLR]
ms.assetid: 0fafd645-0bdf-4d4c-8630-c536fbc4bd2c
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 21bc7b18a375435989a3ac4b612f123cf6e473d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="hashsethasher-stlclr"></a>hash_set::hasher (STL/CLR)
索引鍵雜湊的委派。  
  
## <a name="syntax"></a>語法  
  
```  
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>  
    hasher;  
```  
  
## <a name="remarks"></a>備註  
 此類型描述的委派，將索引鍵的值轉換為整數。  
  
## <a name="example"></a>範例  
  
```  
// cliext_hash_set_hasher.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    Myhash_set::hasher^ myhash = c1.hash_delegate();   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
hash(L'a') = 1616896120  
hash(L'b') = 570892832  
```  
  
## <a name="requirements"></a>需求  
 **標頭：** \<cliext/hash_set >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>請參閱  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md)