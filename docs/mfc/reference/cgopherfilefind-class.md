---
title: CGopherFileFind Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
dev_langs:
- C++
helpviewer_keywords:
- CGopherFileFind [MFC], CGopherFileFind
- CGopherFileFind [MFC], FindFile
- CGopherFileFind [MFC], FindNextFile
- CGopherFileFind [MFC], GetCreationTime
- CGopherFileFind [MFC], GetLastAccessTime
- CGopherFileFind [MFC], GetLastWriteTime
- CGopherFileFind [MFC], GetLength
- CGopherFileFind [MFC], GetLocator
- CGopherFileFind [MFC], GetScreenName
- CGopherFileFind [MFC], IsDots
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
caps.latest.revision: 21
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
ms.openlocfilehash: 174d689708a066afbc307a76ee415d9b4121f577
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cgopherfilefind-class"></a>CGopherFileFind Class
Aids in Internet file searches of gopher servers.  
  
> [!NOTE]
>  The classes `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` and their members have been deprecated because they do not work on the Windows XP platform, but they will continue to work on earlier platforms.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|Constructs a `CGopherFileFind` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CGopherFileFind::FindFile](#findfile)|Finds a file on a gopher server.|  
|[CGopherFileFind::FindNextFile](#findnextfile)|Continues a file search from a previous call to [FindFile](#findfile).|  
|[CGopherFileFind::GetCreationTime](#getcreationtime)|Gets the time the specified file was created.|  
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|Gets the time the specified file was last accessed.|  
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|Gets the time the specified file was last written to.|  
|[CGopherFileFind::GetLength](#getlength)|Gets the length of the found file, in bytes.|  
|[CGopherFileFind::GetLocator](#getlocator)|Get a `CGopherLocator` object.|  
|[CGopherFileFind::GetScreenName](#getscreenname)|Gets the name of a gopher screen.|  
|[CGopherFileFind::IsDots](#isdots)|Tests for the current directory and parent directory markers while iterating through files.|  
  
## <a name="remarks"></a>Remarks  
 `CGopherFileFind` includes member functions that begin a search, locate a file, and return a file's URL.  
  
 Other MFC classes designed for Internet and local file searched include [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) and [CFileFind](../../mfc/reference/cfilefind-class.md). Together with `CGopherFileFind`, these classes provide a seamless mechanism for the user to find specific files, regardless of the server protocol, file type, or location (either a local machine or a remote server.) Note that there is no MFC class for searching on HTTP servers because HTTP does not support the direct file manipulation required by searches.  
  
> [!NOTE]
> `CGopherFileFind` does not support the following member functions of its base class [CFileFind](../../mfc/reference/cfilefind-class.md):  
  
- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)  
  
- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)  
  
- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)  
  
- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)  
  
- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)  
  
 In addition, when used with `CGopherFileFind`, the `CFileFind` member function [IsDots](../../mfc/reference/cfilefind-class.md#isdots) is always **FALSE**.  
  
 For more information about how to use `CGopherFileFind` and the other WinInet classes, see the article [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxinet.h  
  
##  <a name="cgopherfilefind"></a>  CGopherFileFind::CGopherFileFind  
 This member function is called to construct a `CGopherFileFind` object.  
  
```  
explicit CGopherFileFind(
    CGopherConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameters  
 `pConnection`  
 A pointer to a [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) object.  
  
 `dwContext`  
 The context identifier for the operation. See **Remarks** for more information about `dwContext`.  
  
### <a name="remarks"></a>Remarks  
 The default value for `dwContext` is sent by MFC to the `CGopherFileFind` object from the [CInternetSession](../../mfc/reference/cinternetsession-class.md) object that created the `CGopherFileFind` object. When you construct a `CGopherFileFind` object, you can override the default to set the context identifier to a value of your choosing. The context identifier is returned to [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) to provide status on the object with which it is identified. See the article [Internet First Steps: WinInet](../../mfc/wininet-basics.md) for more information about the context identifier.  
  
##  <a name="findfile"></a>  CGopherFileFind::FindFile  
 Call this member function to find a gopher file.  
  
```  
virtual BOOL FindFile(
    CGopherLocator& refLocator,  
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

 
virtual BOOL FindFile(
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>Parameters  
 `refLocator`  
 A reference to a [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) object.  
  
 *pstrString*  
 A pointer to a string containing the file name.  
  
 `dwFlags`  
 The flags describing how to handle this session. The valid flags are:  
  
-   INTERNET_FLAG_RELOAD   Get the data from the remote server even if it is locally cached.  
  
-   INTERNET_FLAG_DONT_CACHE   Do not cache the data, either locally or in any gateways.  
  
-   INTERNET_FLAG_SECURE   Request secure transactions on the wire with Secure Sockets Layer or PCT. This flag is applicable to HTTP requests only.  
  
-   INTERNET_FLAG_USE_EXISTING   If possible, reuse the existing connections to the server for new **FindFile** requests, instead of creating a new session for each request.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; otherwise 0. To get extended error information, call the Win32 function [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Remarks  
 After calling **FindFile** to retrieve the first gopher object, you can call [FindNextFile](#findnextfile) to retrieve subsequent gopher files.  
  
##  <a name="findnextfile"></a>  CGopherFileFind::FindNextFile  
 Call this member function to continue a file search begun with a call to [CGopherFileFind::FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Return Value  
 Nonzero if there are more files; zero if the file found is the last one in the directory or if an error occurred. To get extended error information, call the Win32 function [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). If the file found is the last file in the directory, or if no matching files can be found, the `GetLastError` function returns ERROR_NO_MORE_FILES.  
  
##  <a name="getcreationtime"></a>  CGopherFileFind::GetCreationTime  
 Gets the creation time for the current file.  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `pTimeStamp`  
 A pointer to a [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) structure containing the time the file was created.  
  
 `refTime`  
 A reference to a [CTime](../../atl-mfc-shared/reference/ctime-class.md) object.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; 0 if unsuccessful. `GetCreationTime` returns 0 only if [FindNextFile](#findnextfile) has never been called on this `CGopherFileFind` object.  
  
### <a name="remarks"></a>Remarks  
 You must call [FindNextFile](#findnextfile) at least once before calling `GetCreationTime`.  
  
> [!NOTE]
>  Not all file systems use the same semantics to implement the time stamp returned by this function. This function may return the same value returned by other time stamp functions if the underlying file system or server does not support keeping the time attribute. See the [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure for information about time formats. On some operating systems, the returned time is in the time zone local to the machine were the file is located. See the Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API for more information.  
  
##  <a name="getlastaccesstime"></a>  CGopherFileFind::GetLastAccessTime  
 Gets the time the specified file was last accessed.  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `refTime`  
 A reference to a [CTime](../../atl-mfc-shared/reference/ctime-class.md) object.  
  
 `pTimeStamp`  
 A pointer to a [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) structure containing the time the file was last accessed.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; 0 if unsuccessful. `GetLastAccessTime` returns 0 only if [FindNextFile](#findnextfile) has never been called on this `CGopherFileFind` object.  
  
### <a name="remarks"></a>Remarks  
 You must call [FindNextFile](#findnextfile) at least once before calling `GetLastAccessTime`.  
  
> [!NOTE]
>  Not all file systems use the same semantics to implement the time stamp returned by this function. This function may return the same value returned by other time stamp functions if the underlying file system or server does not support keeping the time attribute. See the [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure for information about time formats. On some operating systems, the returned time is in the time zone local to the machine were the file is located. See the Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API for more information.  
  
##  <a name="getlastwritetime"></a>  CGopherFileFind::GetLastWriteTime  
 Gets the last time the file was changed.  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `pTimeStamp`  
 A pointer to a [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) structure containing the time the file was last written to.  
  
 `refTime`  
 A reference to a [CTime](../../atl-mfc-shared/reference/ctime-class.md) object.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; 0 if unsuccessful. `GetLastWriteTime` returns 0 only if [FindNextFile](#findnextfile) has never been called on this `CGopherFileFind` object.  
  
### <a name="remarks"></a>Remarks  
 You must call [FindNextFile](#findnextfile) at least once before calling `GetLastWriteTime`.  
  
> [!NOTE]
>  Not all file systems use the same semantics to implement the time stamp returned by this function. This function may return the same value returned by other time stamp functions if the underlying file system or server does not support keeping the time attribute. See the [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure for information about time formats. On some operating systems, the returned time is in the time zone local to the machine were the file is located. See the Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API for more information.  
  
##  <a name="getlength"></a>  CGopherFileFind::GetLength  
 Call this member function to get the length, in bytes, of the found file.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The length, in bytes, of the found file.  
  
### <a name="remarks"></a>Remarks  
 `GetLength` uses the Win32 structure [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) to get the value of the file size in bytes.  
  
> [!NOTE]
>  As of MFC 7.0, `GetLength` supports 64-bit integer types. Previously-existing code built with this newer version of the library may result in truncation warnings.  
  
### <a name="example"></a>Example  
  See the example for [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (the base class implementation).  
  
##  <a name="getlocator"></a>  CGopherFileFind::GetLocator  
 Call this member function to get the [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) object that [FindFile](#findfile) uses to find the gopher file.  
  
```  
CGopherLocator GetLocator() const;  
```  
  
### <a name="return-value"></a>Return Value  
 A `CGopherLocator` object.  
  
##  <a name="getscreenname"></a>  CGopherFileFind::GetScreenName  
 Call this member function to get the name of the gopher screen.  
  
```  
CString GetScreenName() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The name of the gopher screen.  
  
##  <a name="isdots"></a>  CGopherFileFind::IsDots  
 Tests for the current directory and parent directory markers while iterating through files.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the found file has the name "." or "..", which indicates that the found file is actually a directory. Otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 You must call [FindNextFile](#findnextfile) at least once before calling `IsDots`.  
  
## <a name="see-also"></a>See Also  
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind Class](../../mfc/reference/cftpfilefind-class.md)   
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)

