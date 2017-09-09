---
title: condition_variable Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- condition_variable/std::condition
- condition_variable/std::condition_variable::condition_variable
- condition_variable/std::condition_variable::native_handle
- condition_variable/std::condition_variable::notify_all
- condition_variable/std::condition_variable::notify_one
- condition_variable/std::condition_variable::wait
- condition_variable/std::condition_variable::wait_for
- condition_variable/std::condition_variable::wait_until
dev_langs:
- C++
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
caps.latest.revision: 16
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
- std::condition
- std::condition_variable::condition_variable
- std::condition_variable::native_handle
- std::condition_variable::notify_all
- std::condition_variable::notify_one
- std::condition_variable::wait
- std::condition_variable::wait_for
- std::condition_variable::wait_until
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 7f6f042a545cc2b9846404551fdc23770b5b19bf
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="conditionvariable-class"></a>condition_variable Class
Use the `condition_variable` class to wait for an event when you have a `mutex` of type `unique_lock<mutex>`. Objects of this type may have better performance than objects of type [condition_variable_any<unique_lock\<mutex>>](../standard-library/condition-variable-any-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```
class condition_variable;
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[condition_variable](#condition_variable)|Constructs a `condition_variable` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[native_handle](#native_handle)|Returns the implementation-specific type representing the condition_variable handle.|  
|[notify_all](#notify_all)|Unblocks all threads that are waiting for the `condition_variable` object.|  
|[notify_one](#notify_one)|Unblocks one of the threads that are waiting for the `condition_variable` object.|  
|[wait](#wait)|Blocks a thread.|  
|[wait_for](#wait_for)|Blocks a thread, and sets a time interval after which the thread unblocks.|  
|[wait_until](#wait_until)|Blocks a thread, and sets a maximum point in time at which the thread unblocks.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<condition_variable>  
  
 **Namespace:** std  
  
##  <a name="condition_variable"></a>  condition_variable::condition_variable Constructor  
 Constructs a `condition_variable` object.  
  
```
condition_variable();
```  
  
### <a name="remarks"></a>Remarks  
 If not enough memory is available, the constructor throws a [system_error](../standard-library/system-error-class.md) object that has a `not_enough_memory` error code. If the object cannot be constructed because some other resource is not available, the constructor throws a `system_error` object that has a `resource_unavailable_try_again` error code.  
  
##  <a name="native_handle"></a>  condition_variable::native_handle  
 Returns the implementation-specific type that represents the condition_variable handle.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Return Value  
 `native_handle_type` is defined as a pointer to Concurrency Runtime internal data structures.  
  
##  <a name="notify_all"></a>  condition_variable::notify_all  
 Unblocks all threads that are waiting for the `condition_variable` object.  
  
```
void notify_all() noexcept;
```  
  
##  <a name="notify_one"></a>  condition_variable::notify_one  
 Unblocks one of the threads that are waiting on the `condition_variable` object.  
  
```
void notify_one() noexcept;
```  
  
##  <a name="wait"></a>  condition_variable::wait  
 Blocks a thread.  
  
```
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```  
  
### <a name="parameters"></a>Parameters  
 `Lck`  
 A [unique_lock\<mutex>](../standard-library/unique-lock-class.md) object.  
  
 `Pred`  
 Any expression that returns `true` or `false`.  
  
### <a name="remarks"></a>Remarks  
 The first method blocks until the `condition_variable` object is signaled by a call to [notify_one](#notify_one) or [notify_all](#notify_all). It can also wake up spuriously.  
  
 In effect, the second method executes the following code.  
  
```cpp  
while(!Pred())
    wait(Lck);
```    
  
##  <a name="wait_for"></a>  condition_variable::wait_for  
 Blocks a thread, and sets a time interval after which the thread unblocks.  
  
```
template <class Rep, class Period>
cv_status wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time);

template <class Rep, class Period, class Predicate>
bool wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>Parameters  
 `Lck`  
 A [unique_lock\<mutex>](../standard-library/unique-lock-class.md) object.  
  
 `Rel_time`  
 A `chrono::duration` object that specifies the amount of time before the thread wakes up.  
  
 `Pred`  
 Any expression that returns `true` or `false`.  
  
### <a name="return-value"></a>Return Value  
 The first method returns `cv_status::timeout` if the wait terminates when `Rel_time` has elapsed. Otherwise, the method returns `cv_status::no_timeout`.  
  
 The second method returns the value of `Pred`.  
  
### <a name="remarks"></a>Remarks  
 The first method blocks until the `condition_variable` object is signaled by a call to [notify_one](#notify_one) or [notify_all](#notify_all) or until the time interval `Rel_time` has elapsed. It can also wake up spuriously.  
  
 In effect, the second method executes the following code.  
  
```cpp  
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
##  <a name="wait_until"></a>  condition_variable::wait_until  
 Blocks a thread, and sets a maximum point in time at which the thread unblocks.  
  
```
template <class Clock, class Duration>
cv_status wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time);

template <class Clock, class Duration, class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time, 
    Predicate Pred);

cv_status wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time);

template <class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>Parameters  
 `Lck`  
 A [unique_lock\<mutex>](../standard-library/unique-lock-class.md) object.  
  
 `Abs_time`  
 A [chrono::time_point](../standard-library/time-point-class.md) object.  
  
 `Pred`  
 Any expression that returns `true` or `false`.  
  
### <a name="return-value"></a>Return Value  
 Methods that return a `cv_status` type return `cv_status::timeout` if the wait terminates when `Abs_time` elapses. Otherwise, the methods return `cv_status::no_timeout`.  
  
 Methods that return a `bool` return the value of `Pred`.  
  
### <a name="remarks"></a>Remarks  
 The first method blocks until the `condition_variable` object is signaled by a call to [notify_one](#notify_one) or [notify_all](#notify_all) or until `Abs_time`. It can also wake up spuriously.  
  
 In effect, the second method executes the following code  
  
```cpp  
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
 The third and fourth methods use a pointer to an object of type `xtime` to replace the `chrono::time_point` object. The `xtime` object specifies the maximum amount of time to wait for a signal.  
  
## <a name="see-also"></a>See Also  
 [Header Files Reference](../standard-library/cpp-standard-library-header-files.md)   
 [<condition_variable>](../standard-library/condition-variable.md)




