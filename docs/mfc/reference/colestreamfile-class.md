---
title: COleStreamFile Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
dev_langs:
- C++
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
caps.latest.revision: 22
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
ms.openlocfilehash: c9ddf0128a69869ea90d151c54fc4fa2d8a613d8
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="colestreamfile-class"></a>COleStreamFile Class
Represents a stream of data ( `IStream`) in a compound file as part of OLE Structured Storage.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleStreamFile : public CFile  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[COleStreamFile::COleStreamFile](#colestreamfile)|Constructs a `COleStreamFile` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[COleStreamFile::Attach](#attach)|Associates a stream with the object.|  
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|Creates a stream from global memory and associates it with the object.|  
|[COleStreamFile::CreateStream](#createstream)|Creates a stream and associates it with the object.|  
|[COleStreamFile::Detach](#detach)|Disassociates the stream from the object.|  
|[COleStreamFile::GetStream](#getstream)|Returns the current stream.|  
|[COleStreamFile::OpenStream](#openstream)|Safely opens a stream and associates it with the object.|  
  
## <a name="remarks"></a>Remarks  
 An `IStorage` object must exist before the stream can be opened or created unless it is a memory stream.  
  
 `COleStreamFile` objects are manipulated exactly like [CFile](../../mfc/reference/cfile-class.md) objects.  
  
 For more information about manipulating streams and storages, see the article [Containers: Compound Files](../../mfc/containers-compound-files.md)..  
  
 For more information, see [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) and [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) in the Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxole.h  
  
##  <a name="attach"></a>  COleStreamFile::Attach  
 Associates the supplied OLE stream with the `COleStreamFile` object.  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>Parameters  
 `lpStream`  
 Points to the OLE stream ( `IStream`) to be associated with the object. Cannot be **NULL**.  
  
### <a name="remarks"></a>Remarks  
 The object must not already be associated with an OLE stream.  
  
 For more information, see [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) in the Windows SDK.  
  
##  <a name="colestreamfile"></a>  COleStreamFile::COleStreamFile  
 Creates a `COleStreamFile` object.  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `lpStream`  
 Pointer to the OLE stream to be associated with the object.  
  
### <a name="remarks"></a>Remarks  
 If `lpStream` is **NULL**, the object is not associated with an OLE stream, otherwise, the object is associated with the supplied OLE stream.  
  
 For more information, see [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) in the Windows SDK.  
  
##  <a name="creatememorystream"></a>  COleStreamFile::CreateMemoryStream  
 Safely creates a new stream out of global, shared memory where a failure is a normal, expected condition.  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `pError`  
 Points to a [CFileException](../../mfc/reference/cfileexception-class.md) object or **NULL** that indicates the completion status of the create operation. Supply this parameter if you want to monitor possible exceptions generated by attempting to create the stream.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the stream is created successfully; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 The memory is allocated by the OLE subsystem.  
  
 For more information, see [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980) in the Windows SDK.  
  
##  <a name="createstream"></a>  COleStreamFile::CreateStream  
 Safely creates a new stream in the supplied storage object where a failure is a normal, expected condition.  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `lpStorage`  
 Points to the OLE storage object that contains the stream to be created. Cannot be **NULL**.  
  
 `lpszStreamName`  
 Name of the stream to be created. Cannot be **NULL**.  
  
 `nOpenFlags`  
 Access mode to use when opening the stream. Exclusive, read/write, and create modes are used by default. For a complete list of the available modes, see [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Points to a [CFileException](../../mfc/reference/cfileexception-class.md) object or **NULL**. Supply this parameter if you want to monitor possible exceptions generated by attempting to create the stream.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the stream is created successfully; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 A file exception will be thrown if the open fails and `pError` is not **NULL**.  
  
 For more information, see [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020) in the Windows SDK.  
  
##  <a name="detach"></a>  COleStreamFile::Detach  
 Disassociates the stream from the object without closing the stream.  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>Return Value  
 A pointer to the stream ( `IStream`) that was associated with the object.  
  
### <a name="remarks"></a>Remarks  
 The stream must be closed in some other fashion before the program terminates.  
  
 For more information, see [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) in the Windows SDK.  
  
##  <a name="getstream"></a>  COleStreamFile::GetStream  
 Call this function to return a pointer to current stream.  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>Return Value  
 A pointer to the current stream interface ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)).  
  
##  <a name="openstream"></a>  COleStreamFile::OpenStream  
 Opens an existing stream.  
  
```  
BOOL OpenStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `lpStorage`  
 Points to the OLE storage object that contains the stream to be opened. Cannot be **NULL**.  
  
 `lpszStreamName`  
 Name of the stream to be opened. Cannot be **NULL**.  
  
 `nOpenFlags`  
 Access mode to use when opening the stream. Exclusive and read/write modes are used by default. For the complete list of the available modes, see [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Points to a [CFileException](../../mfc/reference/cfileexception-class.md) object or **NULL**. Supply this parameter if you want to monitor possible exceptions generated by attempting to open the stream.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the stream is opened successfully; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 A file exception will be thrown if the open fails and `pError` is not **NULL**.  
  
 For more information, see [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025) in the Windows SDK.  
  
## <a name="see-also"></a>See Also  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)




