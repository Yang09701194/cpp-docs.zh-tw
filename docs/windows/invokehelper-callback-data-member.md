---
title: 'Invokehelper:: Callback_ 資料成員 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper::callback_
dev_langs:
- C++
helpviewer_keywords:
- callback_ data member
ms.assetid: 6f0cbf6d-0448-46f8-ba71-bd6fd8702e3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0d6d767a77b68ad8585da711861d942abbe6b686
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013489"
---
# <a name="invokehelpercallback-data-member"></a>InvokeHelper::callback_ 資料成員
支援 WRL 結構，而且不是直接從您的程式碼使用。  
  
## <a name="syntax"></a>語法  
  
```cpp  
TCallback callback_;  
```  
  
## <a name="remarks"></a>備註  
 表示事件發生時要呼叫的事件處理常式。  
  
 `TCallback`範本參數會指定事件處理常式的類型。  
  
## <a name="requirements"></a>需求  
 **標頭：** event.h  
  
 **命名空間：** Microsoft::WRL::Details  
  
## <a name="see-also"></a>另請參閱  
 [InvokeHelper 結構](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details 命名空間](../windows/microsoft-wrl-details-namespace.md)