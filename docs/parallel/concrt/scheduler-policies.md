---
title: 排程器原則
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler policies
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
ms.openlocfilehash: 0f90b461ecba702501c2f6919572dc828c80907f
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142274"
---
# <a name="scheduler-policies"></a>排程器原則

本檔說明並行執行階段中排程器原則的角色。 排程器*原則*會控制排程器在管理工作時所使用的策略。 例如，請考慮要求某些工作執行 `THREAD_PRIORITY_NORMAL` 以及要求其他工作執行 `THREAD_PRIORITY_HIGHEST` 的應用程式。  您可以建立兩個排程器執行個體：一個將 `ContextPriority` 原則指定為 `THREAD_PRIORITY_NORMAL`，另一個將同一個原則指定為 `THREAD_PRIORITY_HIGHEST`。

使用排程器原則，您就可以分割可用處理資源，並將一組固定的資源指派給每個排程器。 例如，請考慮不會擴充至超過四個處理器的平行演算法。 您可以建立排程器原則，將其工作限制為不超過四個處理器同時使用。

> [!TIP]
> 並行執行階段會提供預設排程器。 因此，您不需要在應用程式中自行建立。 由於工作排程器可協助您微調應用程式的效能，因此如果您不熟悉並行執行階段，建議您從[平行模式程式庫（PPL）](../../parallel/concrt/parallel-patterns-library-ppl.md)或[非同步代理](../../parallel/concrt/asynchronous-agents-library.md)程式程式庫開始。

當您使用 concurrency：： [CurrentScheduler：： create](reference/currentscheduler-class.md#create)、concurrency：：排程器[：： create](reference/scheduler-class.md#create)或[concurrency：：](reference/scheduler-class.md#setdefaultschedulerpolicy)排程器：： SetDefaultSchedulerPolicy 方法來建立排程器實例時，您會提供[concurrency：： SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md)物件，其中包含指定排程器行為的機碼值組集合。 `SchedulerPolicy` 的函式會採用可變數目的引數。 第一個引數是您即將指定的原則元素數目。 其餘的引數是每個原則元素的機碼值組。 下列範例會建立一個指定三個原則元素的 `SchedulerPolicy` 物件。 對於未指定的原則機碼，執行階段會使用預設值。

[!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/cpp/scheduler-policies_1.cpp)]

[Concurrency：:P olicyelementkey](reference/concurrency-namespace-enums.md#policyelementkey)列舉會定義與工作排程器相關聯的原則索引鍵。 下表描述原則索引鍵，以及執行時間針對每一個所使用的預設值。

|原則金鑰|描述|預設值|
|----------------|-----------------|-------------------|
|`SchedulerKind`|[Concurrency：： SchedulerType](reference/concurrency-namespace-enums.md#schedulertype)值，指定要用來排程工作的執行緒類型。|`ThreadScheduler` (使用一般執行緒)。 這是這個金鑰的唯一有效值。|
|`MaxConcurrency`|`unsigned int` 值，指定排程器使用的並行資源數目上限。|[concurrency：： MaxExecutionResources](reference/concurrency-namespace-constants1.md#maxexecutionresources)|
|`MinConcurrency`|`unsigned int` 值，指定排程器所使用的並行資源最小數目。|`1`|
|`TargetOversubscriptionFactor`|`unsigned int` 值，指定要配置給每個處理資源的執行緒數目。|`1`|
|`LocalContextCacheSize`|`unsigned int` 值，指定可在每個虛擬處理器的本機佇列中快取的內容數目上限。|`8`|
|`ContextStackSize`|`unsigned int` 值，指定要為每個內容保留的堆疊大小（以 kb 為單位）。|`0` （使用預設堆疊大小）|
|`ContextPriority`|`int` 值，指定每個內容的執行緒優先順序。 這可以是任何您可以傳遞至[SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority)或 `INHERIT_THREAD_PRIORITY`的值。|`THREAD_PRIORITY_NORMAL`|

|`SchedulingProtocol`|[Concurrency：： SchedulingProtocolType](reference/concurrency-namespace-enums.md#schedulingprotocoltype)值，指定要使用的排程演算法。 |`EnhanceScheduleGroupLocality`| |`DynamicProgressFeedback`|[Concurrency：:D ynamicprogressfeedbacktype](reference/concurrency-namespace-enums.md#dynamicprogressfeedbacktype)值，指定是否要根據以統計資料為基礎的進度資訊來重新平衡資源。<br /><br /> **注意**請勿將此原則設定為 `ProgressFeedbackDisabled`，因為它已保留供執行時間使用。 |`ProgressFeedbackEnabled`|

每個排程器會在排程工作時，使用自己的原則。 與某個排程器相關聯的原則並不會影響任何其他排程器的行為。 此外，建立 `Scheduler` 物件之後，您就無法變更排程器原則。

> [!IMPORTANT]
> 僅使用排程器原則來控制執行時間所建立之執行緒的屬性。 不要變更執行緒同質性或執行階段所建立的執行緒優先權，因為這樣可能會造成未定義的行為發生。

如果您未明確建立排程器，執行時間會為您建立預設排程器。 如果您想要在應用程式中使用預設排程器，但想要為該排程器指定要使用的原則，請先呼叫[concurrency：： schedule：： SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)方法，再排定平行工作。 如果您未呼叫 `Scheduler::SetDefaultSchedulerPolicy` 方法，執行時間會使用資料表中的預設原則值。

使用[concurrency：： CurrentScheduler：： GetPolicy](reference/currentscheduler-class.md#getpolicy)和[concurrency：：排程器：： GetPolicy](reference/scheduler-class.md#getpolicy)方法來取出排程器原則的複本。 您從這些方法收到的原則值可能會與您在建立排程器時指定的原則值不同。

## <a name="example"></a>範例

若要檢查使用特定排程器原則來控制排程器行為的範例，請參閱[如何：指定特定](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)排程器原則和[如何：建立使用特定](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)排程器原則的代理程式。

## <a name="see-also"></a>另請參閱

[工作排程器](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[如何：指定特定排程器原則](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br/>
[如何：建立使用特定排程器原則的代理程式](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
