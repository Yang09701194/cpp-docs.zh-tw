---
title: recursive_mutex Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::recursive_mutex
- mutex/std::recursive_mutex::recursive_mutex
- mutex/std::recursive_mutex::lock
- mutex/std::recursive_mutex::try_lock
- mutex/std::recursive_mutex::unlock
dev_langs:
- C++
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
caps.latest.revision: 9
author: corob-msft
ms.author: corob
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
helpviewer_keywords:
- std::recursive_mutex [C++]
- std::recursive_mutex [C++], recursive_mutex
- std::recursive_mutex [C++], lock
- std::recursive_mutex [C++], try_lock
- std::recursive_mutex [C++], unlock
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: b95335a0b67f7345dd61a1de5d6da4589055dc72
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="recursivemutex-class"></a>recursive_mutex Class
Represents a *mutex type*. In contrast to [mutex](../standard-library/mutex-class-stl.md), the behavior of calls to locking methods for objects that are already locked is well-defined.  
  
## <a name="syntax"></a>Syntax  
  
```
class recursive_mutex;
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[recursive_mutex](#recursive_mutex)|Constructs a `recursive_mutex` object.|  
|[~recursive_mutex Destructor](#dtorrecursive_mutex_destructor)|Releases any resources that are used by the `recursive_mutex` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[lock](#lock)|Blocks the calling thread until the thread obtains ownership of the mutex.|  
|[try_lock](#try_lock)|Attempts to obtain ownership of the mutex without blocking.|  
|[unlock](#unlock)|Releases ownership of the mutex.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<mutex>  
  
 **Namespace:** std  
  
##  <a name="lock"></a>  lock  
 Blocks the calling thread until the thread obtains ownership of the `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Remarks  
 If the calling thread already owns the `mutex`, the method returns immediately, and the previous lock remains in effect.  
  
##  <a name="recursive_mutex"></a>  recursive_mutex  
 Constructs a `recursive_mutex` object that is not locked.  
  
```cpp  
recursive_mutex();
```  
  
##  <a name="dtorrecursive_mutex_destructor"></a>  ~recursive_mutex  
 Releases any resources that are used by the object.  
  
```cpp  
~recursive_mutex();
```  
  
### <a name="remarks"></a>Remarks  
 If the object is locked when the destructor runs, the behavior is undefined.  
  
##  <a name="try_lock"></a>  try_lock  
 Attempts to obtain ownership of the `mutex` without blocking.  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>Return Value  
 `true` if the method successfully obtains ownership of the `mutex` or if the calling thread already owns the `mutex`; otherwise, `false`.  
  
### <a name="remarks"></a>Remarks  
 If the calling thread already owns the `mutex`, the function immediately returns `true`, and the previous lock remains in effect.  
  
##  <a name="unlock"></a>  unlock  
 Releases ownership of the mutex.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Remarks  
 This method releases ownership of the `mutex` only after it is called as many times as [lock](#lock) and [try_lock](#try_lock) have been called successfully on the `recursive_mutex` object.  
  
 If the calling thread does not own the `mutex`, the behavior is undefined.  
  
## <a name="see-also"></a>See Also  
 [Header Files Reference](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




