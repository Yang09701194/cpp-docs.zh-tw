---
title: Internet URL Parsing Globals and Helpers | Microsoft Docs
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.isapi
dev_langs:
- C++
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
caps.latest.revision: 14
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
ms.openlocfilehash: 675b7cced508fbd03b36948004d2312e5525b908
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="internet-url-parsing-globals-and-helpers"></a>Internet URL Parsing Globals and Helpers
When a client sends a query to the Internet server, you can use one of the URL parsing globals to extract information about the client. The helper functions provide other internet functionality.
  
## <a name="internet-url-parsing-globals"></a>Internet URL Parsing Globals  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|Parses a URL string and returns the type of service and its components.|  
|[AfxParseURLEx](#afxparseurlex)|Parses a URL string and returns the type of service and its components, as well as providing the user name and password.|  

## <a name="other-internet-helpers"></a>Other Internet Helpers
|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|Throws an exception related to the internet connection.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|Determines the type of an Internet handle.|
  
##  <a name="afxparseurl"></a>  AfxParseURL  
 This global is used in [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort); 
```  
  
### <a name="parameters"></a>Parameters  
 *pstrURL*  
 A pointer to a string containing the URL to be parsed.  
  
 `dwServiceType`  
 Indicates the type of Internet service. Possible values are as follows:  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 The first segment of the URL following the service type.  
  
 `strObject`  
 An object that the URL refers to (may be empty).  
  
 `nPort`  
 Determined from either the Server or Object portions of the URL, if either exists.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the URL was successfully parsed; otherwise, 0 if it is empty or does not contain a known Internet service type.  
  
### <a name="remarks"></a>Remarks  
 It parses a URL string and returns the type of service and its components.  
  
 For example, `AfxParseURL` parses URLs of the form **service://server/dir/dir/object.ext:port** and returns its components stored as follows:  
  
 `strServer` == "server"  
  
 `strObject` == "/dir/dir/object/object.ext"  
  
 `nPort` == #port  
  
 `dwServiceType` == #service  
  
> [!NOTE]
>  To call this function, your project must include AFXINET.H.  
  
### <a name="requirements"></a>Requirements  
  **Header** afxinet.h  
  
##  <a name="afxparseurlex"></a>  AfxParseURLEx  
 This global function is the extended version of [AfxParseURL](#afxparseurl) and is used in [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort,  
    CString& strUsername,  
    CString& strPassword,  
    DWORD dwFlags = 0); 
```  
  
### <a name="parameters"></a>Parameters  
 *pstrURL*  
 A pointer to a string containing the URL to be parsed.  
  
 `dwServiceType`  
 Indicates the type of Internet service. Possible values are as follows:  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 The first segment of the URL following the service type.  
  
 `strObject`  
 An object that the URL refers to (may be empty).  
  
 `nPort`  
 Determined from either the Server or Object portions of the URL, if either exists.  
  
 *strUsername*  
 A reference to a `CString` object containing the name of the user.  
  
 `strPassword`  
 A reference to a `CString` object containing the password of the user.  
  
 `dwFlags`  
 The flags controlling how to parse the URL. Can be a combination of the following values:  
  
|Value|Meaning|  
|-----------|-------------|  
|**ICU_DECODE**|Convert %XX escape sequences to characters.|  
|**ICU_NO_ENCODE**|Do not convert unsafe characters to escape sequence.|  
|**ICU_NO_META**|Do not remove meta sequences (such as "\ ." and "\ ..") from the URL.|  
|**ICU_ENCODE_SPACES_ONLY**|Encode spaces only.|  
|**ICU_BROWSER_MODE**|Do not encode or decode characters after '#' or '', and do not remove trailing white space after ''. If this value is not specified, the entire URL is encoded and trailing white space is removed.|  
  
 If you use the MFC default, which is no flags, the function converts all unsafe characters and meta sequences (such as \\.,\ .., and \\...) to escape sequences.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the URL was successfully parsed; otherwise, 0 if it is empty or does not contain a known Internet service type.  
  
### <a name="remarks"></a>Remarks  
 It parses a URL string and returns the type of service and its components, as well as providing the user's name and password. The flags indicate how unsafe characters are handled.  
  
> [!NOTE]
>  To call this function, your project must include AFXINET.H.  

### <a name="requirements"></a>Requirements  
  **Header** afxinet.h  
    
## <a name="see-also"></a>See Also  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)
 
## <a name="afxgetinternethandletype"></a>  AfxGetInternetHandleType
Use this global function to determine the type of an Internet handle.  
   
### <a name="syntax"></a>Syntax  
  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );  
```
### <a name="parameters"></a>Parameters  
 `hQuery`  
 A handle to an Internet query.  
   
### <a name="return-value"></a>Return Value  
 Any of the Internet service types defined by WININET.H. See the Remarks section for a list of these Internet services. If the handle is NULL or not recognized, the function returns AFX_INET_SERVICE_UNK.  
   
### <a name="remarks"></a>Remarks  
 The following list includes possible Internet types returned by `AfxGetInternetHandleType`.  
  
-   INTERNET_HANDLE_TYPE_INTERNET  
  
-   INTERNET_HANDLE_TYPE_CONNECT_FTP  
  
-   INTERNET_HANDLE_TYPE_CONNECT_GOPHER  
  
-   INTERNET_HANDLE_TYPE_CONNECT_HTTP  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_HTTP_REQUEST  
  
> [!NOTE]
>  In order to call this function, your project must include AFXINET.H.  
   
### <a name="requirements"></a>Requirements  
 **Header:** afxinet.h  
   
### <a name="see-also"></a>See Also  
 [Macros and Globals](mfc-macros-and-globals.md)   
 [AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
 
## <a name="afxthrowinternetexception"></a>  AfxThrowInternetException
Throws an Internet exception.  
   
### <a name="syntax"></a>Syntax    
```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );  
```
### <a name="parameters"></a>Parameters  
 `dwContext`  
 The context identifier for the operation that caused the error. The default value of `dwContext` is specified originally in [CInternetSession](cinternetsession-class.md) and is passed to [CInternetConnection](cinternetconnection-class.md)- and [CInternetFile](cinternetfile-class.md)-derived classes. For specific operations performed on a connection or a file, you usually override the default with a `dwContext` of your own. This value then is returned to [CInternetSession::OnStatusCallback](cinternetsession-class.md#onstatuscallback) to identify the specific operation's status. 
  
 `dwError`  
 The error that caused the exception.  
   
### <a name="remarks"></a>Remarks  
 You are responsible for determining the cause based on the operating-system error code.  
  
> [!NOTE]
>  To call this function, your project must include AFXINET.H.  
   
### <a name="requirements"></a>Requirements  
 **Header:** afxinet.h  
   
### <a name="see-also"></a>See Also  
 [Macros and Globals](mfc-macros-and-globals.md)   
 [CInternetException Class](cinternetexception-class.md)   
 [THROW](#throw)
 


