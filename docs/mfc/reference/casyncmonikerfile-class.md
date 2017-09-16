---
title: CAsyncMonikerFile Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
dev_langs:
- C++
helpviewer_keywords:
- CAsyncMonikerFile [MFC], CAsyncMonikerFile
- CAsyncMonikerFile [MFC], Close
- CAsyncMonikerFile [MFC], GetBinding
- CAsyncMonikerFile [MFC], GetFormatEtc
- CAsyncMonikerFile [MFC], Open
- CAsyncMonikerFile [MFC], CreateBindStatusCallback
- CAsyncMonikerFile [MFC], GetBindInfo
- CAsyncMonikerFile [MFC], GetPriority
- CAsyncMonikerFile [MFC], OnDataAvailable
- CAsyncMonikerFile [MFC], OnLowResource
- CAsyncMonikerFile [MFC], OnProgress
- CAsyncMonikerFile [MFC], OnStartBinding
- CAsyncMonikerFile [MFC], OnStopBinding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
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
ms.translationtype: MT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: d188df15c70be6eb32bb53f72eb974ac286d723e
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="casyncmonikerfile-class"></a>CAsyncMonikerFile Class
Provides functionality for the use of asynchronous monikers in ActiveX controls (formerly OLE controls).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|Constructs a `CAsyncMonikerFile` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CAsyncMonikerFile::Close](#close)|Closes and releases all resources.|  
|[CAsyncMonikerFile::GetBinding](#getbinding)|Retrieves a pointer to the asynchronous transfer binding.|  
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|Retrieves the format of the data in the stream.|  
|[CAsyncMonikerFile::Open](#open)|Opens a file asynchronously.|  
  
### <a name="protected-methods"></a>Protected Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|Creates a COM object that implements `IBindStatusCallback`.|  
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|Called by the OLE system library to request information on the type of bind to be created.|  
|[CAsyncMonikerFile::GetPriority](#getpriority)|Called by the OLE system library to get the priority of the binding.|  
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|Called to provide data as it becomes available to the client during asynchronous bind operations.|  
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|Called when resources are low.|  
|[CAsyncMonikerFile::OnProgress](#onprogress)|Called to indicate progress on the data downloading process.|  
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|Called when binding is starting up.|  
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|Called when asynchronous transfer is stopped.|  
  
## <a name="remarks"></a>Remarks  
 Derived from [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), which in turn is derived from [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` uses the [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) interface to access any data stream asynchronously, including loading files asynchronously from a URL. The files can be datapath properties of ActiveX controls.  
  
 Asynchronous monikers are used primarily in Internet-enabled applications and ActiveX controls to provide a responsive user-interface during file transfers. A prime example of this is the use of [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) to provide asynchronous properties for ActiveX controls. The `CDataPathProperty` object will repeatedly get a callback to indicate availability of new data during a lengthy property exchange process.  
  
 For more information about how to use asynchronous monikers and ActiveX controls in Internet applications, see the following articles:  
  
- [Internet First Steps: Asynchronous Monikers](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
- [Internet First Steps: ActiveX Controls](../../mfc/activex-controls-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxole.h  
  
##  <a name="casyncmonikerfile"></a>  CAsyncMonikerFile::CAsyncMonikerFile  
 Constructs a `CAsyncMonikerFile` object.  
  
```  
CAsyncMonikerFile();
```  
  
### <a name="remarks"></a>Remarks  
 It does not create the `IBindHost` interface. `IBindHost` is used only if you provide it in the **Open** member function.  
  
 For a description of the `IBindHost` interface, see the Windows SDK.  
  
##  <a name="close"></a>  CAsyncMonikerFile::Close  
 Call this function to close and release all resources.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarks  
 Can be called on unopened or already closed files.  
  
##  <a name="createbindstatuscallback"></a>  CAsyncMonikerFile::CreateBindStatusCallback  
 Creates a COM object that implements `IBindStatusCallback`.  
  
```  
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```  
  
### <a name="parameters"></a>Parameters  
 `pUnkControlling`  
 A pointer to the controlling unknown (the outer **IUnknown**) or **NULL** if aggregation is not being used.  
  
### <a name="return-value"></a>Return Value  
 If `pUnkControlling` is not **NULL**, the function returns a pointer to the inner **IUnknown** on a new COM object supporting `IBindStatusCallback`. If `pUnkControlling` is **NULL**, the function returns a pointer to an **IUnknown** on a new COM object supporting `IBindStatusCallback`.  
  
### <a name="remarks"></a>Remarks  
 `CAsyncMonikerFile` requires a COM object that implements `IBindStatusCallback`. MFC implements such an object, and it is aggregatable. You can override `CreateBindStatusCallback` to return your own COM object. Your COM object can aggregate MFC's implementation by calling `CreateBindStatusCallback` with the controlling unknown of your COM object. COM objects implemented using the `CCmdTarget` COM support can retrieve the controlling unknown using **CCmdTarget::GetControllingUnknown**.  
  
 Alternately, your COM object can delegate to MFC's implementation by calling **CreateBindStatusCallback( NULL )**.  
  
 [CAsyncMonikerFile::Open](#open) calls `CreateBindStatusCallback`.  
  
 For more information about asynchronous monikers and asynchronous binding, see the [IBindStatusCallback](http://msdn.microsoft.com/library/ie/ms775060) interface and [How Asynchronous Binding and Storage Work](http://msdn.microsoft.com/library/windows/desktop/aa379152). For a discussion of aggregation, see [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558). All three topics are in the Windows SDK.  
  
##  <a name="getbindinfo"></a>  CAsyncMonikerFile::GetBindInfo  
 Called from the client of an asynchronous moniker to tell the asynchronous moniker how it wants to bind.  
  
```  
virtual DWORD GetBindInfo() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Retrieves the settings for **IBindStatusCallBack**. For a description of the `IBindStatusCallback` interface, see the Windows SDK.  
  
### <a name="remarks"></a>Remarks  
 The default implementation sets the binding to be asynchronous, to use a storage medium (a stream), and to use the data-push model. Override this function if you want to change the behavior of the binding.  
  
 One reason for doing this would be to bind using the data-pull model instead of the data-push model. In a data-pull model, the client drives the bind operation, and the moniker only provides data to the client when it is read. In a data-push model, the moniker drives the asynchronous bind operation and continuously notifies the client whenever new data is available.  
  
##  <a name="getbinding"></a>  CAsyncMonikerFile::GetBinding  
 Call this function to retrieve a pointer to the asynchronous transfer binding.  
  
```  
IBinding* GetBinding() const;  
```  
  
### <a name="return-value"></a>Return Value  
 A pointer to the `IBinding` interface provided when asynchronous transfer begins. Returns **NULL** if for any reason the transfer cannot be made asynchronously.  
  
### <a name="remarks"></a>Remarks  
 This allows you to control the data transfer process through the `IBinding` interface, for example, with **IBinding::Abort**, **IBinding::Pause**, and **IBinding::Resume**.  
  
 For a description of the `IBinding` interface, see the Windows SDK.  
  
##  <a name="getformatetc"></a>  CAsyncMonikerFile::GetFormatEtc  
 Call this function to retrieve the format of the data in the stream.  
  
```  
FORMATETC* GetFormatEtc() const;  
```  
  
### <a name="return-value"></a>Return Value  
 A pointer to the Windows structure [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) for the currently opened stream. Returns **NULL** if the moniker has not been bound, if it is not asynchronous, or if the asynchronous operation has not begun.  
  
##  <a name="getpriority"></a>  CAsyncMonikerFile::GetPriority  
 Called from the client of an asynchronous moniker as the binding process starts to receive the priority given to the thread for the binding operation.  
  
```  
virtual LONG GetPriority() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The priority at which the asynchronous transfer will take place. One of the standard thread priority flags: **THREAD_PRIORITY_ABOVE_NORMAL**, **THREAD_PRIORITY_BELOW_NORMAL**, **THREAD_PRIORITY_HIGHEST**, **THREAD_PRIORITY_IDLE**, **THREAD_PRIORITY_LOWEST**, **THREAD_PRIORITY_NORMAL**, and **THREAD_PRIORITY_TIME_CRITICAL**. See the Windows function [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) for a description of these values.  
  
### <a name="remarks"></a>Remarks  
 `GetPriority` should not be called directly. **THREAD_PRIORITY_NORMAL** is returned by the default implementation.  
  
##  <a name="ondataavailable"></a>  CAsyncMonikerFile::OnDataAvailable  
 An asynchronous moniker calls `OnDataAvailable` to provide data to the client as it becomes available, during asynchronous bind operations.  
  
```  
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```  
  
### <a name="parameters"></a>Parameters  
 `dwSize`  
 The cumulative amount (in bytes) of data available since the beginning of the binding. Can be zero, indicating that the amount of data is not relevant to the operation, or that no specific amount became available.  
  
 *bscfFlag*  
 A **BSCF** enumeration value. Can be one or more of the following values:  
  
- **BSCF_FIRSTDATANOTIFICATION** Identifies the first call to `OnDataAvailable` for a given bind operation.  
  
- **BSCF_INTERMEDIATEDATANOTIFICATION** Identifies an intermediary call to `OnDataAvailable` for a bind operation.  
  
- **BSCF_LASTDATANOTIFICATION** Identifies the last call to `OnDataAvailable` for a bind operation.  
  
### <a name="remarks"></a>Remarks  
 The default implementation of this function does nothing. See the following example for a sample implementation.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]  
  
##  <a name="onlowresource"></a>  CAsyncMonikerFile::OnLowResource  
 Called by the moniker when resources are low.  
  
```  
virtual void OnLowResource();
```  
  
### <a name="remarks"></a>Remarks  
 The default implementation calls `GetBinding( )-> Abort( )`.  
  
##  <a name="onprogress"></a>  CAsyncMonikerFile::OnProgress  
 Called by the moniker repeatedly to indicate the current progress of this bind operation, typically at reasonable intervals during a lengthy operation.  
  
```  
virtual void OnProgress(
    ULONG ulProgress,  
    ULONG ulProgressMax,  
    ULONG ulStatusCode,  
    LPCTSTR szStatusText);
```  
  
### <a name="parameters"></a>Parameters  
 `ulProgress`  
 Indicates the current progress of the bind operation relative to the expected maximum indicated in `ulProgressMax`.  
  
 `ulProgressMax`  
 Indicates the expected maximum value of `ulProgress` for the duration of calls to `OnProgress` for this operation.  
  
 `ulStatusCode`  
 Provides additional information regarding the progress of the bind operation. Valid values are taken from the `BINDSTATUS` enumeration. See Remarks for possible values.  
  
 `szStatusText`  
 Information about the current progress, depending on the value of `ulStatusCode`. See Remarks for possible values.  
  
### <a name="remarks"></a>Remarks  
 Possible values for `ulStatusCode` (and the `szStatusText` for each value) are:  
  
 **BINDSTATUS_FINDINGRESOURCE**  
 The bind operation is finding the resource that holds the object or storage being bound to. The `szStatusText` provides the display name of the resource being searched for (for example, "www.microsoft.com").  
  
 **BINDSTATUS_CONNECTING**  
 The bind operation is connecting to the resource that holds the object or storage being bound to. The `szStatusText` provides the display name of the resource being connected to (for example, an IP address).  
  
 **BINDSTATUS_SENDINGREQUEST**  
 The bind operation is requesting the object or storage being bound to. The `szStatusText` provides the display name of the object (for example, a file name).  
  
 **BINDSTATUS_REDIRECTING**  
 The bind operation has been redirected to a different data location. The `szStatusText` provides the display name of the new data location.  
  
 **BINDSTATUS_USINGCACHEDCOPY**  
 The bind operation is retrieving the requested object or storage from a cached copy. The `szStatusText` is **NULL**.  
  
 **BINDSTATUS_BEGINDOWNLOADDATA**  
 The bind operation has begun receiving the object or storage being bound to. The `szStatusText` provides the display name of the data location.  
  
 **BINDSTATUS_DOWNLOADINGDATA**  
 The bind operation continues to receive the object or storage being bound to. The `szStatusText` provides the display name of the data location.  
  
 **BINDSTATUS_ENDDOWNLOADDATA**  
 The bind operation has finished receiving the object or storage being bound to. The `szStatusText` provides the display name of the data location.  
  
 **BINDSTATUS_CLASSIDAVAILABLE**  
 An instance of the object being bound to is just about to be created. The `szStatusText` provides the CLSID of the new object in string format, allowing the client an opportunity to cancel the bind operation, if desired.  
  
##  <a name="onstartbinding"></a>  CAsyncMonikerFile::OnStartBinding  
 Override this function in your derived classes to perform actions when binding is starting up.  
  
```  
virtual void OnStartBinding();
```  
  
### <a name="remarks"></a>Remarks  
 This function is called back by the moniker. The default implementation does nothing.  
  
##  <a name="onstopbinding"></a>  CAsyncMonikerFile::OnStopBinding  
 Called by the moniker at the end of the bind operation.  
  
```  
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```  
  
### <a name="parameters"></a>Parameters  
 `hresult`  
 An `HRESULT` that is the error or warning value.  
  
 *szErrort*  
 A character string describing the error.  
  
### <a name="remarks"></a>Remarks  
 Override this function to perform actions when the transfer is stopped. By default, the function releases `IBinding`.  
  
 For a description of the `IBinding` interface, see the Windows SDK.  
  
##  <a name="open"></a>  CAsyncMonikerFile::Open  
 Call this member function to open a file asynchronously.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `lpszURL`  
 A pointer to file to be opened asynchronously. The file can be any valid URL or filename.  
  
 `pError`  
 A pointer to the file exceptions. In the event of an error, it will be set to the cause.  
  
 `pMoniker`  
 A pointer to the asynchronous moniker interface `IMoniker`, a precise moniker that is the combination of the document's own moniker, which you can retrieve with **IOleClientSite::GetMoniker(** *OLEWHICHMK_CONTAINER* **)**, and a moniker created from the path name. The control can use this moniker to bind, but this is not the moniker the control should save.  
  
 *pBindHost*  
 A pointer to the `IBindHost` interface that will be used to create the moniker from a potentially relative pathname. If the bind host is invalid or does not provide a moniker, the call defaults to **Open(** `lpszFileName`**,**`pError`**)**. For a description of the `IBindHost` interface, see the Windows SDK.  
  
 `pServiceProvider`  
 A pointer to the `IServiceProvider` interface. If the service provider is invalid or fails to provide the service for `IBindHost`, the call defaults to **Open(** `lpszFileName`**,**`pError`**)**.  
  
 *pUnknown*  
 A pointer to the **IUnknown** interface. If `IServiceProvider` is found, the function queries for `IBindHost`. If the service provider is invalid or fails to provide the service for `IBindHost`, the call defaults to **Open(** `lpszFileName`**,**`pError`**)**.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the file is opened successfully; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 This call initiates the binding process.  
  
 You can use a URL or a filename for the `lpszURL` parameter. For example:  
  
 [!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]  
  
 - or -  
  
 [!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]  
  
## <a name="see-also"></a>See Also  
 [CMonikerFile Class](../../mfc/reference/cmonikerfile-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CMonikerFile Class](../../mfc/reference/cmonikerfile-class.md)   
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)

