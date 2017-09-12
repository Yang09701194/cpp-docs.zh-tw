---
title: SOCKADDR Structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 269d20023d1f95a82c62244a0e77b2b902ba0b19
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="sockaddr-structure"></a>SOCKADDR Structure
The `SOCKADDR` structure is used to store an Internet Protocol (IP) address for a machine participating in a Windows Sockets communication.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct sockaddr {  
    unsigned short sa_family;  
    char sa_data[14];  
};  
```  
  
#### <a name="parameters"></a>Parameters  
 *sa_family*  
 Socket address family.  
  
 *sa_data*  
 Maximum size of all the different socket address structures.  
  
## <a name="remarks"></a>Remarks  
 The Microsoft TCP/IP Sockets Developer's Kit only supports the Internet address domains. To actually fill in values for each part of an address, you use the `SOCKADDR_IN` data structure, which is specifically for this address format. The `SOCKADDR` and the `SOCKADDR_IN` data structures are the same size. You simply cast to switch between the two structure types.  
  
## <a name="requirements"></a>Requirements  
 **Header:** winsock2.h  
  
## <a name="see-also"></a>See Also  
 [Structures, Styles, Callbacks, and Message Maps](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR_IN Structure](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)   
 [CSocket::Create](../../mfc/reference/csocket-class.md#create)


