---
title: '&lt;future&gt; enums | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 9343cd3d49c6574aafbf039a06625dfcd6a3519f
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ltfuturegt-enums"></a>&lt;future&gt; enums
||||  
|-|-|-|  
|[future_errc](#future_errc)|[future_status](#future_status)|[launch](#launch)|  
  
##  <a name="future_errc"></a>  future_errc Enumeration  
 Supplies symbolic names for all of the errors that are reported by the [future_error](../standard-library/future-error-class.md) class.  
  
class future_errc { broken_promise, future_already_retrieved, promise_already_satisfied, no_state };  
  
##  <a name="future_status"></a>  future_status Enumeration  
 Supplies symbolic names for the reasons that a timed wait function can return.  
  
```
enum future_status{    ready,
    timeout,
 deferred};
```  
  
##  <a name="launch"></a>  launch Enumeration  
 Represents a bitmask type that describes the possible modes for the template function [async](../standard-library/future-functions.md#async).  
  
class launch{ async, deferred };  
  
## <a name="see-also"></a>See Also  
 [\<future>](../standard-library/future.md)




