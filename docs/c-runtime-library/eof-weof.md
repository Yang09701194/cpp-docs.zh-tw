---
title: "EOF、WEOF | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EOF
dev_langs: C++
helpviewer_keywords:
- EOF function
- WEOF function
- end of file
ms.assetid: a7150563-cdae-4cdf-9798-ad509990e505
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d2aa2496683f10b0f603839d27104bd0e28fa50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="eof-weof"></a>EOF、WEOF
## <a name="syntax"></a>語法  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>備註  
 遇到檔案結尾 (或某些情況下發生錯誤) 時，I/O 常式會傳回 EOF。  
  
 WEOF 產生的傳回值類型為 **wint_t**，用來表示寬資料流的結尾，或報告錯誤狀況。  
  
## <a name="see-also"></a>另請參閱  
 [putc、putwc](../c-runtime-library/reference/putc-putwc.md)   
 [ungetc、ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)   
 [scanf、_scanf_l、wscanf、_wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [fflush](../c-runtime-library/reference/fflush.md)   
 [fclose、_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)   
 [_ungetch、_ungetwch、_ungetch_nolock、_ungetwch_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)   
 [_putch、_putwch](../c-runtime-library/reference/putch-putwch.md)   
 [isascii、__isascii、iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)   
 [全域常數](../c-runtime-library/global-constants.md)