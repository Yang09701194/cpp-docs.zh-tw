---
title: condition_variable_any Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- condition_variable/std::condition_variable_any
- condition_variable/std::condition_variable_any::condition_variable_any
- condition_variable/std::condition_variable_any::notify_all
- condition_variable/std::condition_variable_any::notify_one
- condition_variable/std::condition_variable_any::wait
- condition_variable/std::condition_variable_any::wait_for
- condition_variable/std::condition_variable_any::wait_until
dev_langs:
- C++
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
caps.latest.revision: 15
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
- std::condition_variable_any
- std::condition_variable_any::condition_variable_any
- std::condition_variable_any::notify_all
- std::condition_variable_any::notify_one
- std::condition_variable_any::wait
- std::condition_variable_any::wait_for
- std::condition_variable_any::wait_until
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: bbb4ce1dc861727543608fcea3261621e5251dad
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="conditionvariableany-class"></a>condition_variable_any Class
Use the class `condition_variable_any` to wait for an event that has any `mutex` type.  
  
## <a name="syntax"></a>Syntax  
  
```
class condition_variable_any;
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[condition_variable_any](#condition_variable_any)|Constructs a `condition_variable_any` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[notify_all](#notify_all)|Unblocks all threads that are waiting for the `condition_variable_any` object.|  
|[notify_one](#notify_one)|Unblocks one of the threads that are waiting for the `condition_variable_any` object.|  
|[wait](#wait)|Blocks a thread.|  
|[wait_for](#wait_for)|Blocks a thread, and sets a time interval after which the thread unblocks.|  
|[wait_until](#wait_until)|Blocks a thread, and sets a maximum point in time at which the thread unblocks.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<condition_variable>  
  
 **Namespace:** std  
  
##  <a name="condition_variable_any"></a>  condition_variable_any::condition_variable_any Constructor  
 Constructs a `condition_variable_any` object.  
  
```
condition_variable_any();
```  
  
### <a name="remarks"></a>Remarks  
 If not enough memory is available, the constructor throws a [system_error](../standard-library/system-error-class.md) object that has a `not_enough_memory` error code. If the object cannot be constructed because some other resource is not available, the constructor throws a `system_error` object that has a `resource_unavailable_try_again` error code.  
  
##  <a name="notify_all"></a>  condition_variable_any::notify_all  
 Unblocks all threads that are waiting for the `condition_variable_any` object.  
  
```
void notify_all() noexcept;
```  
  
##  <a name="notify_one"></a>  condition_variable_any::notify_one  
 Unblocks one of the threads that are waiting on the `condition_variable_any` object.  
  
```
void notify_one() noexcept;
```  
  
##  <a name="wait"></a>  condition_variable_any::wait  
 Blocks a thread.  
  
```
template <class Lock>  
void wait(Lock& Lck);

template <class Lock, class Predicate>
void wait(Lock& Lck, Predicate Pred);
```  
  
### <a name="parameters"></a>Parameters  
 `Lck`  
 A `mutex` object of any type.  
  
 `Pred`  
 Any expression that returns `true` or `false`.  
  
### <a name="remarks"></a>Remarks  
 The first method blocks until the `condition_variable_any` object is signaled by a call to [notify_one](../standard-library/condition-variable-class.md#notify_one) or [notify_all](../standard-library/condition-variable-class.md#notify_all). It can also wake up spuriously.  
  
 The second method in effect executes the following code.  
  
```
while (!Pred())
    wait(Lck);
```    
  
##  <a name="wait_for"></a>  condition_variable_any::wait_for  
 Blocks a thread, and sets a time interval after which the thread unblocks.  
  
```
template <class Lock, class Rep, class Period>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time);

template <class Lock, class Rep, class Period, class Predicate>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time, Predicate Pred);
```  
  
### <a name="parameters"></a>Parameters  
 `Lck`  
 A `mutex` object of any type.  
  
 `Rel_time`  
 A `chrono::duration` object that specifies the amount of time before the thread wakes up.  
  
 `Pred`  
 Any expression that returns `true` or `false`.  
  
### <a name="return-value"></a>Return Value  
 The first method returns `cv_status::timeout` if the wait terminates when `Rel_time` has elapsed. Otherwise, the method returns `cv_status::no_timeout`.  
  
 The second method returns the value of `Pred`.  
  
### <a name="remarks"></a>Remarks  
 The first method blocks until the `condition_variable_any` object is signaled by a call to [notify_one](../standard-library/condition-variable-class.md#notify_one) or [notify_all](../standard-library/condition-variable-class.md#notify_all), or until the time interval `Rel_time` has elapsed. It can also wake up spuriously.  
  
 The second method in effect executes the following code.  
  
```cpp  
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
##  <a name="wait_until"></a>  condition_variable_any::wait_until  
 Blocks a thread, and sets a maximum point in time at which the thread unblocks.  
  
```
template <class Lock, class Clock, class Duration>
void wait_until(Lock& Lck, const chrono::time_point<Clock, Duration>& Abs_time);

template <class Lock, class Clock, class Duration, class Predicate>
void wait_until(
    Lock& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

template <class Lock>
void wait_until(Lock Lck, const xtime* Abs_time);

template <class Lock, class Predicate>
void wait_until(
    Lock Lck,
    const xtime* Abs_time,
    Predicate Pred);
```  
  
### <a name="parameters"></a>Parameters  
 `Lck`  
 A mutex object.  
  
 `Abs_time`  
 A [chrono::time_point](../standard-library/time-point-class.md) object.  
  
 `Pred`  
 Any expression that returns `true` or `false`.  
  
### <a name="return-value"></a>Return Value  
 Methods that return a `cv_status` type return `cv_status::timeout` if the wait terminates when `Abs_time` elapses. Otherwise, the methods return `cv_status::no_timeout`.  
  
 Methods that return a `bool` return the value of `Pred`.  
  
### <a name="remarks"></a>Remarks  
 The first method blocks until the `condition_variable` object is signaled by a call to [notify_one](../standard-library/condition-variable-class.md#notify_one) or [notify_all](../standard-library/condition-variable-class.md#notify_all), or until `Abs_time`. It can also wake up spuriously.  
  
 The second method in effect executes the following code.  
  
```
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
 The third and fourth methods use a pointer to an object of type `xtime` to replace the `chrono::time_point` object. The `xtime` object specifies the maximum amount of time to wait for a signal.  
  
## <a name="see-also"></a>See Also  
 [Header Files Reference](../standard-library/cpp-standard-library-header-files.md)   
 [<condition_variable>](../standard-library/condition-variable.md)




