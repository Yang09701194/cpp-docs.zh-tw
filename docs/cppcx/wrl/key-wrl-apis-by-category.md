---
title: 依分類區分的重要 WRL 應用程式開發介面
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
ms.openlocfilehash: 8ac89f3286866ac61bac5ae256bdb448fe88f07d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213820"
---
# <a name="key-wrl-apis-by-category"></a>依分類區分的重要 WRL 應用程式開發介面

下表列出主要 Windows 執行階段C++範本庫類別、結構、函數和宏。 Helper 命名空間和類別中的結構會被省略。 這些清單會擴大以命名空間排列的 API 檔。

## <a name="classes"></a>類別

|Title|描述|
|-----------|-----------------|
|[ActivationFactory 類別](activationfactory-class.md)|讓 Windows 執行階段啟動一或多個類別。|
|[AsyncBase 類別](asyncbase-class.md)|實作 Windows 執行階段非同步狀態機器。|
|[ClassFactory 類別](classfactory-class.md)|實作 `IClassFactory` 介面的基本功能。|
|[ComPtr 類別](comptr-class.md)|建立代表範本參數所指定之介面的 *「智慧型指標」* (Smart Pointer) 類型。 ComPtr 自動維護基礎介面指標的參考計數，並在參考計數歸零時釋放介面。|
|[Event 類別 (Windows 執行階段 C++ 範本庫)](event-class-wrl.md)|表示事件。|
|[EventSource 類別](eventsource-class.md)|表示事件。 `EventSource` 成員函式會新增、移除及叫用事件處理常式。|
|[FtmBase 類別](ftmbase-class.md)|代表無限制執行緒封送處理器物件。|
|[HandleT 類別](handlet-class.md)|表示物件的控制碼。|
|[HString 類別](hstring-class.md)|提供操作 HSTRING 控制碼的支援。|
|[HStringReference 類別](hstringreference-class.md)|表示從現有字串建立的 HSTRING。|
|[Module 類別](module-class.md)|表示相關物件的集合。|
|[Module::GenericReleaseNotifier 類別](module-genericreleasenotifier-class.md)|當目前模組中的最後一個物件釋放時，叫用事件處理常式。 事件處理常式是由 lambda、仿函數或指標對函式所指定。|
|[Module::MethodReleaseNotifier 類別](module-methodreleasenotifier-class.md)|當目前模組中的最後一個物件釋放時，叫用事件處理常式。 事件處理常式是由物件和其指標對方法成員所指定。|
|[Module::ReleaseNotifier 類別](module-releasenotifier-class.md)|釋放模組中的最後一個物件時，叫用事件處理常式。|
|[RoInitializeWrapper 類別](roinitializewrapper-class.md)|初始化 Windows 執行階段。|
|[RuntimeClass 類別](runtimeclass-class.md)|表示繼承指定數目的介面的具現化類別，並提供指定的 Windows 執行階段、傳統 COM 和弱式參考支援。|
|[SimpleActivationFactory 類別](simpleactivationfactory-class.md)|提供基本機制以建立 Windows 執行階段或傳統 COM 基底類別。|
|[SimpleClassFactory 類別](simpleclassfactory-class.md)|提供基本機制以建立基底類別。|
|[WeakRef 類別](weakref-class.md)|代表 *弱式參考* 僅供 Windows 執行階段使用，而不供傳統 COM 使用。 弱式參考代表不一定可存取的物件。|

## <a name="structures"></a>結構

|Title|描述|
|-----------|-----------------|
|[ChainInterfaces 結構](chaininterfaces-structure.md)|指定可以套用至一組介面 ID 的驗證和初始化函式。|
|[CloakedIid 結構](cloakediid-structure.md)|指出在 IID 清單中無法存取指定介面的 `RuntimeClass`、`Implements` 和 `ChainInterfaces` 範本。|
|[Implements 結構](implements-structure.md)|針對指定的介面，執行 `QueryInterface` 和 `GetIid`。|
|[MixIn 結構](mixin-structure.md)|確保執行階段類別衍生自 Windows 執行階段介面 (若有的話)，然後才是傳統 COM 介面。|

## <a name="functions"></a>Functions

|Title|描述|
|-----------|-----------------|
|[ActivateInstance 函式](activateinstance-function.md)|註冊並抓取指定的類別識別碼中所定義之指定類型的實例。|
|[AsWeak 函式](asweak-function.md)|擷取指定執行個體的弱式參考。|
|[回呼函式](callback-function-wrl.md)|建立成員函式是回呼方法的物件。|
|[CreateActivationFactory 函式](createactivationfactory-function.md)|建立會產生指定類別之執行個體 (由 Windows 執行階段啟動) 的處理站。|
|[CreateClassFactory 函式](createclassfactory-function.md)|建立會產生指定類別之執行個體的處理站。|
|[GetActivationFactory 函式](getactivationfactory-function.md)|抓取範本參數所指定之類型的啟用 factory。|
|[Make 函式](make-function.md)|初始化指定的 Windows 執行階段類別。|

## <a name="macros"></a>巨集

|Title|描述|
|-----------|-----------------|
|[ActivatableClass 巨集](activatableclass-macros.md)|填入內部快取，其中包含可建立指定類別之實例的 factory。|
|[InspectableClass 巨集](inspectableclass-macro.md)|設定執行時間類別名稱和信任層級。|

## <a name="see-also"></a>另請參閱

[Windows 執行階段 C++ 範本庫 (WRL)](windows-runtime-cpp-template-library-wrl.md)
