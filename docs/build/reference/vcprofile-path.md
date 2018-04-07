---
title: VCPROFILE_PATH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VCPROFILE_PATH
dev_langs:
- C++
helpviewer_keywords:
- VCPROFILE_PATH environment variable
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea682b70f4417ef49bfca530af5f12f21699a389
ms.sourcegitcommit: 5cd2e3e51ecc8d9fc0d889555b4bfa193ba1d6a5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2018
---
# <a name="vcprofilepath"></a>VCPROFILE_PATH
指定要建立的.pgc 檔案的目錄。  
  
## <a name="syntax"></a>語法  
  
```  
VCPROFILE_PATH=path  
```  
  
#### <a name="parameters"></a>參數  
 `path`  
 將加入的.pgc 檔案的目錄路徑。  
  
## <a name="remarks"></a>備註  
 根據預設，.pgc 檔案的建立與所分析的二進位檔相同的目錄中。  不過，如果二進位檔的絕對路徑不存在，作為可能的情況下，當您從建置二進位的一部電腦上執行設定檔的案例，您可以設定`VCPROFILE_PATH`存在的路徑。  
  
## <a name="example"></a>範例  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## <a name="see-also"></a>另請參閱  
 [特性指引最佳化的環境變數](../../build/reference/environment-variables-for-profile-guided-optimizations.md)