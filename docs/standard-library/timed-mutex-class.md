---
title: timed_mutex Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::timed_mutex
- mutex/std::timed_mutex::timed_mutex
- mutex/std::timed_mutex::lock
- mutex/std::timed_mutex::try_lock
- mutex/std::timed_mutex::try_lock_for
- mutex/std::timed_mutex::try_lock_until
- mutex/std::timed_mutex::unlock
dev_langs:
- C++
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
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
- std::timed_mutex [C++]
- std::timed_mutex [C++], timed_mutex
- std::timed_mutex [C++], lock
- std::timed_mutex [C++], try_lock
- std::timed_mutex [C++], try_lock_for
- std::timed_mutex [C++], try_lock_until
- std::timed_mutex [C++], unlock
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 3c57c0b274f45b34088698851dc3fe30d784a22b
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="timedmutex-class"></a>timed_mutex Class
Represents a *timed mutex type*. Objects of this type are used to enforce mutual exclusion through time-limited blocking within a program.  
  
## <a name="syntax"></a>Syntax  
  
```
class timed_mutex;
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[timed_mutex](#timed_mutex)|Constructs a `timed_mutex` object that's not locked.|  
|[timed_mutex::~timed_mutex Destructor](#dtortimed_mutex_destructor)|Releases any resources that are used by the `timed_mutex` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[lock](#lock)|Blocks the calling thread until the thread obtains ownership of the `mutex`.|  
|[try_lock](#try_lock)|Attempts to obtain ownership of the `mutex` without blocking.|  
|[try_lock_for](#try_lock_for)|Attempts to obtain ownership of the `mutex` for a specified time interval.|  
|[try_lock_until](#try_lock_until)|Attempts to obtain ownership of the `mutex` until a specified time.|  
|[unlock](#unlock)|Releases ownership of the `mutex`.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<mutex>  
  
 **Namespace:** std  
  
##  <a name="lock"></a>  timed_mutex::lock
 Blocks the calling thread until the thread obtains ownership of the `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Remarks  
 If the calling thread already owns the `mutex`, the behavior is undefined.  
  
##  <a name="timed_mutex"></a>  timed_mutex::timed_mutex Constructor  
 Constructs a `timed_mutex` object that is not locked.  
  
```cpp  
timed_mutex();
```  
  
##  <a name="dtortimed_mutex_destructor"></a>  timed_mutex::~timed_mutex Destructor  
 Releases any resources that are used by the `mutex` object.  
  
```cpp  
~timed_mutex();
```  
  
### <a name="remarks"></a>Remarks  
 If the object is locked when the destructor runs, the behavior is undefined.  
  
##  <a name="try_lock"></a>  timed_mutex::try_lock
 Attempts to obtain ownership of the `mutex` without blocking.  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>Return Value  
 `true` if the method successfully obtains ownership of the `mutex`; otherwise, `false`.  
  
### <a name="remarks"></a>Remarks  
 If the calling thread already owns the `mutex`, the behavior is undefined.  
  
##  <a name="try_lock_for"></a>  timed_mutex::try_lock_for
 Attempts to obtain ownership of the `mutex` without blocking.  
  
```cpp  
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Parameters  
 `Rel_time`  
 A [chrono::duration](../standard-library/duration-class.md) object that specifies the maximum amount of time that the method attempts to obtain ownership of the `mutex`.  
  
### <a name="return-value"></a>Return Value  
 `true` if the method successfully obtains ownership of the `mutex`; otherwise, `false`.  
  
### <a name="remarks"></a>Remarks  
 If the calling thread already owns the `mutex`, the behavior is undefined.  
  
##  <a name="try_lock_until"></a>  timed_mutex::try_lock_until
 Attempts to obtain ownership of the `mutex` without blocking.  
  
```cpp  
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```  
  
### <a name="parameters"></a>Parameters  
 `Abs_time`  
 A point in time that specifies the threshold after which the method no longer attempts to obtain ownership of the `mutex`.  
  
### <a name="return-value"></a>Return Value  
 `true` if the method successfully obtains ownership of the `mutex`; otherwise, `false`.  
  
### <a name="remarks"></a>Remarks  
 If the calling thread already owns the `mutex`, the behavior is undefined.  
  
##  <a name="unlock"></a>  timed_mutex::unlock
 Releases ownership of the `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Remarks  
 If the calling thread does not own the `mutex`, the behavior is undefined.  
  
## <a name="see-also"></a>See Also  
 [Header Files Reference](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




