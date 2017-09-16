---
title: '&lt;future&gt; functions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
caps.latest.revision: 11
manager: ghogen
helpviewer_keywords:
- std::async [C++]
- std::future_category [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::swap [C++]
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 96c09f6b90a0c531a7dcc916512247d0fa4084b2
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ltfuturegt-functions"></a>&lt;future&gt; functions
||||  
|-|-|-|  
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|  
|[make_error_condition](#make_error_condition)|[swap](#swap)|  
  
##  <a name="async"></a>  async  
 Represents an *asynchronous provider*.  
  
```
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```  
  
### <a name="parameters"></a>Parameters  
 `policy`  
 A [launch](../standard-library/future-enums.md#launch) value.  
  
### <a name="remarks"></a>Remarks  
 Definitions of abbreviations:  
  
|||  
|-|-|  
|*dfn*|The result of calling `decay_copy(forward<Fn>(fn))`.|  
|*dargs*|The results of the calls `decay_copy(forward<ArgsTypes>(args...))`.|  
|*Ty*|The type `result_of<Fn(ArgTypes...)>::type`.|  
  
 The first template function returns `async(launch::any, fn, args...)`.  
  
 The second function returns a `future<Ty>` object whose *associated asynchronous state* holds a result together with the values of *dfn* and *dargs* and a thread object to manage a separate thread of execution.  
  
 Unless `decay<Fn>::type` is a type other than launch, the second function does not participate in overload resolution.  
  
 If `policy` is `launch::any`, the function might choose `launch::async` or `launch::deferred`. In this implementation, the function uses `launch::async`.  
  
 If `policy` is `launch::async`, the function creates a thread that evaluates `INVOKE(dfn, dargs..., Ty)`. The function returns after it creates the thread without waiting for results. If the system can't start a new thread, the function throws a [system_error](../standard-library/system-error-class.md) that has an error code of `resource_unavailable_try_again`.  
  
 If `policy` is `launch::deferred`, the function marks its associated asynchronous state as holding a *deferred function* and returns. The first call to any non-timed function that waits for the associated asynchronous state to be ready in effect calls the deferred function by evaluating `INVOKE(dfn, dargs..., Ty)`.  
  
 In all cases, the associated asynchronous state of the `future` object is not set to *ready* until the evaluation of `INVOKE(dfn, dargs..., Ty)` completes, either by throwing an exception or by returning normally. The result of the associated asynchronous state is an exception if one was thrown, or any value that's returned by the evaluation.  
  
> [!NOTE]
>  For a `future`—or the last [shared_future](../standard-library/shared-future-class.md)—that's attached to a task started with `std::async`, the destructor blocks if the task has not completed; that is, it blocks if this thread did not yet call `.get()` or `.wait()` and the task is still running. If a `future` obtained from `std::async` is moved outside the local scope, other code that uses it must be aware that its destructor may block for the shared state to become ready.  
  
 The pseudo-function `INVOKE` is defined in [\<functional>](../standard-library/functional.md).  
  
##  <a name="future_category"></a>  future_category  
 Returns a reference to the [error_category](../standard-library/error-category-class.md) object that characterizes errors that are associated with `future` objects.  
  
```
const error_category& future_category() noexcept;
```  
  
##  <a name="make_error_code"></a>  make_error_code  
 Creates an [error_code](../standard-library/error-code-class.md) together with the [error_category](../standard-library/error-category-class.md) object that characterizes [future](../standard-library/future-class.md) errors.  
  
```
inline error_code make_error_code(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>Parameters  
 `Errno`  
 A [future_errc](../standard-library/future-enums.md#future_errc) value that identifies the reported error.  
  
### <a name="return-value"></a>Return Value  
 `error_code(static_cast<int>(Errno), future_category());`  
  
##  <a name="make_error_condition"></a>  make_error_condition  
 Creates an [error_condition](../standard-library/error-condition-class.md) together with the [error_category](../standard-library/error-category-class.md) object that characterizes [future](../standard-library/future-class.md) errors.  
  
```
inline error_condition make_error_condition(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>Parameters  
 `Errno`  
 A [future_errc](../standard-library/future-enums.md#future_errc) value that identifies the reported error.  
  
### <a name="return-value"></a>Return Value  
 `error_condition(static_cast<int>(Errno), future_category());`  
  
##  <a name="swap"></a>  swap  
 Exchanges the *associated asynchronous state* of one `promise` object with that of another.  
  
```
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```  
  
### <a name="parameters"></a>Parameters  
 `Left`  
 The left `promise` object.  
  
 `Right`  
 The right `promise` object.  
  
## <a name="see-also"></a>See Also  
 [\<future>](../standard-library/future.md)




