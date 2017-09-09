---
title: shared_future Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::shared_future
- future/std::shared_future::shared_future
- future/std::shared_future::get
- future/std::shared_future::valid
- future/std::shared_future::wait
- future/std::shared_future::wait_for
- future/std::shared_future::wait_until
dev_langs:
- C++
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
caps.latest.revision: 13
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
- std::shared_future [C++]
- std::shared_future [C++], shared_future
- std::shared_future [C++], get
- std::shared_future [C++], valid
- std::shared_future [C++], wait
- std::shared_future [C++], wait_for
- std::shared_future [C++], wait_until
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 14f427af73abbe511ecdd326240388cc29da16df
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="sharedfuture-class"></a>shared_future Class
Describes an *asynchronous return object*. In contrast with a [future](../standard-library/future-class.md) object, an *asynchronous provider* can be associated with any number of `shared_future` objects.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
class shared_future;
```  
  
## <a name="remarks"></a>Remarks  
 Do not call any methods other than `valid`, `operator=`, and the destructor on a `shared_future` object that's *empty*.  
  
 `shared_future` objects are not synchronized. Calling methods on the same object from multiple threads introduces a data race that has unpredictable results.  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[shared_future](#shared_future)|Constructs a `shared_future` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[get](#get)|Retrieves the result that's stored in the *associated asynchronous state*.|  
|[valid](#valid)|Specifies whether the object is not empty.|  
|[wait](#wait)|Blocks the current thread until the associated asynchronous state is ready.|  
|[wait_for](#wait_for)|Blocks until the associated asynchronous state is ready or until the specified time has elapsed.|  
|[wait_until](#wait_until)|Blocks until the associated asynchronous state is ready or until a specified point in time.|  
  
### <a name="public-operators"></a>Public Operators  
  
|Name|Description|  
|----------|-----------------|  
|[shared_future::operator=](#op_eq)|Assigns a new associated asynchronous state.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<future>  
  
 **Namespace:** std  
  
##  <a name="get"></a>  shared_future::get
 Retrieves the result that's stored in the *associated asynchronous state*.  
  
```
const Ty& get() const;

Ty& get() const;

void get() const;
```  
  
### <a name="remarks"></a>Remarks  
 If the result is an exception, the method rethrows it. Otherwise, the result is returned.  
  
 Before it retrieves the result, this method blocks the current thread until the associated asynchronous state is ready.  
  
 For the partial specialization `shared_future<Ty&>`, the stored value is effectively a reference to the object that was passed to the *asynchronous provider* as the return value.  
  
 Because no stored value exists for the specialization `shared_future<void>`, the method returns `void`.  
  
##  <a name="op_eq"></a>  shared_future::operator=  
 Transfers an *associated asynchronous state* from a specified object.  
  
```
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```  
  
### <a name="parameters"></a>Parameters  
 `Right`  
 A `shared_future` object.  
  
### <a name="return-value"></a>Return Value  
 `*this`  
  
### <a name="remarks"></a>Remarks  
 For the first operator, `Right` no longer has an associated asynchronous state after the operation.  
  
 For the second method, `Right` maintains its associated asynchronous state.  
  
##  <a name="shared_future"></a>  shared_future::shared_future Constructor  
 Constructs a `shared_future` object.  
  
```
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```  
  
### <a name="parameters"></a>Parameters  
 `Right`  
 A [future](../standard-library/future-class.md) or `shared_future` object.  
  
### <a name="remarks"></a>Remarks  
 The first constructor constructs a `shared_future` object that has no *associated asynchronous state*.  
  
 The second and third constructors construct a `shared_future` object and transfer the associated asynchronous state from `Right`. `Right` no longer has an associated asynchronous state.  
  
 The fourth constructor constructs a `shared_future` object that has the same associated asynchronous state as `Right`.  
  
##  <a name="valid"></a>  shared_future::valid
 Specifies whether the object has an *associated asynchronous state*.  
  
```
bool valid() noexcept;
```  
  
### <a name="return-value"></a>Return Value  
 `true` if the object has an associated asynchronous state; otherwise, `false`.  
  
##  <a name="wait"></a>  shared_future::wait
 Blocks the current thread until the *associated asynchronous state* is *ready*.  
  
```
void wait() const;
```  
  
### <a name="remarks"></a>Remarks  
 An associated asynchronous state is ready only if its asynchronous provider has stored a return value or stored an exception.  
  
##  <a name="wait_for"></a>  shared_future::wait_for
 Blocks the current thread until the associated asynchronous state is *ready* or until a specified time has elapsed.  
  
```
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```  
  
### <a name="parameters"></a>Parameters  
 `Rel_time`  
 A [chrono::duration](../standard-library/duration-class.md) object that specifies a maximum time interval that the thread blocks.  
  
### <a name="return-value"></a>Return Value  
 A [future_status](../standard-library/future-enums.md#future_status) that indicates the reason for returning.  
  
### <a name="remarks"></a>Remarks  
 An associated asynchronous state is *ready* only if its asynchronous provider has stored a return value or stored an exception.  
  
##  <a name="wait_until"></a>  shared_future::wait_until
 Blocks the current thread until the associated asynchronous state is *ready* or until after a specified time point.  
  
```
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```  
  
### <a name="parameters"></a>Parameters  
 `Abs_time`  
 A [chrono::time_point](../standard-library/time-point-class.md) object that specifies a time after which the thread can unblock.  
  
### <a name="return-value"></a>Return Value  
 A [future_status](../standard-library/future-enums.md#future_status) that indicates the reason for returning.  
  
### <a name="remarks"></a>Remarks  
 An associated asynchronous state is ready only if its asynchronous provider has stored a return value or stored an exception.  
  
## <a name="see-also"></a>See Also  
 [Header Files Reference](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)




