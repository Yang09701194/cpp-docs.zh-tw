---
title: CDataSource 類別
ms.date: 11/04/2016
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
- ATL::CDataSource::Close
- ATL.CDataSource.Close
- CDataSource::Close
- CDataSource.Close
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
- CDataSource::GetProperties
- ATL.CDataSource.GetProperties
- CDataSource.GetProperties
- ATL::CDataSource::GetProperties
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
- CDataSource::OpenFromFileName
- ATL::CDataSource::OpenFromFileName
- OpenFromFileName
- CDataSource.OpenFromFileName
- ATL.CDataSource.OpenFromFileName
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
helpviewer_keywords:
- CDataSource class
- Close method
- GetInitializationString method
- GetProperties method
- GetProperty method
- Open method
- OpenFromFileName method
- OpenFromInitializationString method
- OpenWithPromptFileName method
- OpenWithServiceComponents method
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
ms.openlocfilehash: 646d4b3548a1c5ee1bdfaf64f7823fa584abaac5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212006"
---
# <a name="cdatasource-class"></a>CDataSource 類別

對應至 OLE DB 資料來源物件，其表示透過提供者與資料來源的連線。

## <a name="syntax"></a>語法

```cpp
class CDataSource
```

## <a name="requirements"></a>需求

**標題:** atldbcli.h

## <a name="members"></a>成員

### <a name="methods"></a>方法

|||
|-|-|
|[關閉](#close)|關閉連接。|
|[GetInitializationString](#getinitializationstring)|擷取目前開啟之資料來源的初始化字串。|
|[GetProperties](#getproperties)|取得目前針對所連線之資料來源設定的屬性值。|
|[GetProperty](#getproperty)|取得目前針對所連線資料來源設定的單一屬性值。|
|[開啟](#open)|使用 `CLSID`、`ProgID`或呼叫者所提供的 `CEnumerator` 標記，建立與提供者（資料來源）的連接。|
|[OpenFromFileName](#openfromfilename)|從以使用者提供的檔名指定的檔案，開啟資料來源。|
|[OpenFromInitializationString](#openfrominitializationstring)|開啟以初始化字串指定的資料來源。|
|[OpenWithPromptFileName](#openwithpromptfilename)|允許使用者選取先前建立的資料連結檔案，以開啟對應的資料來源。|
|[OpenWithServiceComponents](#openwithservicecomponents)|使用 [資料連結] 對話方塊開啟資料來源物件。|

## <a name="remarks"></a>備註

可為單一連線建立一個或多個資料庫工作階段。 這些工作階段是以 `CSession` 表示。 您必須先呼叫[CDataSource：： open](../../data/oledb/cdatasource-open.md)來開啟連接，才能使用 `CSession::Open`建立會話。

如需如何使用 `CDataSource`的範例，請參閱[CatDB](../../overview/visual-cpp-samples.md)範例。

## <a name="cdatasourceclose"></a><a name="close"></a>CDataSource：： Close

藉由釋放 `m_spInit` 指標來關閉連接。

### <a name="syntax"></a>語法

```cpp
void Close() throw();
```

## <a name="cdatasourcegetinitializationstring"></a><a name="getinitializationstring"></a>CDataSource：： GetInitializationString

抓取目前開啟之資料來源的初始化字串。

### <a name="syntax"></a>語法

```cpp
HRESULT GetInitializationString(BSTR* pInitializationString,
   bool bIncludePassword = false) throw();
```

#### <a name="parameters"></a>參數

*pInitializationString*<br/>
脫銷初始化字串的指標。

*bIncludePassword*<br/>
在如果字串包含密碼，則為**true** ;否則**為 false**。

### <a name="return-value"></a>傳回值

標準 HRESULT。

### <a name="remarks"></a>備註

產生的初始化字串可以用來稍後重新開啟此資料來源連接。

## <a name="cdatasourcegetproperties"></a><a name="getproperties"></a>CDataSource：： GetProperties

傳回針對連接的資料來源物件所要求的屬性資訊。

### <a name="syntax"></a>語法

```cpp
HRESULT GetProperties(ULONG ulPropIDSets,
   constDBPROPIDSET* pPropIDSet,
   ULONG* pulPropertySets,
   DBPROPSET** ppPropsets) const throw();
```

#### <a name="parameters"></a>參數

請參閱 Windows SDK 中 OLE DB 程式設計*人員參考*中的[IDBProperties：： GetProperties](/previous-versions/windows/desktop/ms714344(v=vs.85)) 。

### <a name="return-value"></a>傳回值

標準 HRESULT。

### <a name="remarks"></a>備註

若要取得單一屬性，請使用[GetProperty](../../data/oledb/cdatasource-getproperty.md)。

## <a name="cdatasourcegetproperty"></a><a name="getproperty"></a>CDataSource：： GetProperty

針對連接的資料來源物件，傳回指定之屬性的值。

### <a name="syntax"></a>語法

```cpp
HRESULT GetProperty(const GUID& guid,
   DBPROPID propid,
   VARIANT* pVariant) const throw();
```

#### <a name="parameters"></a>參數

*guid*<br/>
在GUID，識別要傳回屬性的屬性集。

*propid*<br/>
在要傳回之屬性的屬性識別碼。

*pVariant*<br/>
脫銷Variant 的指標，其中 `GetProperty` 會傳回屬性的值。

### <a name="return-value"></a>傳回值

標準 HRESULT。

### <a name="remarks"></a>備註

若要取得多個屬性，請使用[GetProperties](../../data/oledb/cdatasource-getproperties.md)。

## <a name="cdatasourceopen"></a><a name="open"></a>CDataSource：： Open

使用 `CLSID`、`ProgID`或 `CEnumerator` 的名字，開啟與資料來源的連接，或使用 [定位器] 對話方塊來提示使用者。

### <a name="syntax"></a>語法

```cpp
HRESULT Open(const CLSID& clsid,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CLSID& clsid,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();HRESULT Open(LPCTSTR szProgID,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();HRESULT Open(LPCTSTR szProgID,
   LPCTSTR pName,  LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(const CEnumerator& enumerator,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CEnumerator& enumerator,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(HWND hWnd = GetActiveWindow(),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET) throw();

HRESULT Open(LPCWSTR szProgID,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(LPCSTR szProgID,
   LPCTSTR pName,LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();
```

#### <a name="parameters"></a>參數

*clsid*<br/>
在資料提供者的 `CLSID`。

*傳入 ppropset*<br/>
在[DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))結構陣列的指標，其中包含要設定的屬性和值。 請參閱 Windows SDK 中 OLE DB 程式設計*人員參考*中的[屬性集和屬性群組](/previous-versions/windows/desktop/ms713696(v=vs.85))。

*nPropertySets*<br/>
在在*傳入 ppropset*引數中傳遞的[DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))結構數目。

*pName*<br/>
[in] 要連接的資料庫名稱。

*pUserName*<br/>
[in] 使用者的名稱。

*pPassword*<br/>
[in] 使用者的密碼。

*nInitMode*<br/>
[in] 資料庫初始化模式。 如需有效初始化模式的清單，請參閱 Windows SDK 中 OLE DB 程式設計*人員參考*中的[初始化屬性](/previous-versions/windows/desktop/ms723127(v=vs.85))。 如果*nInitMode*為零，則不會在用來開啟連接的屬性集內包含任何初始化模式。

*szProgID*<br/>
[in] 程式識別碼。

*enumerator*<br/>
在當呼叫端未指定 `CLSID`時，用來取得開啟連接之標記的[CEnumerator](../../data/oledb/cenumerator-class.md)物件。

*hWnd*<br/>
[in] 做為對話方塊之父視窗的控制代碼。 使用使用*hWnd*參數的函數多載會自動叫用服務元件;如需詳細資訊，請參閱備註。

*dwPromptOptions*<br/>
[in] 決定要顯示的定位程式對話方塊樣式。 請參閱 Msdasc.h 中的可能值。

### <a name="return-value"></a>傳回值

標準 HRESULT。

### <a name="remarks"></a>備註

使用*hWnd*參數的方法多載會使用 oledb32.dll 中的服務元件開啟資料來源物件。此 DLL 包含服務元件功能的執行，例如資源分享、自動交易登記等。 如需詳細資訊，請參閱 OLE DB 程式設計[人員指南](/previous-versions/windows/desktop/ms713643(v=vs.85))中的 OLE DB 參考。

不使用*hWnd*參數的方法多載會開啟資料來源物件，而不使用 oledb32.dll 中的服務元件。 使用這些函式多載開啟的[CDataSource](../../data/oledb/cdatasource-class.md)物件將無法使用任何服務元件功能。

### <a name="example"></a>範例

下列程式碼示範如何使用 OLE DB 範本開啟 Jet 4.0 資料來源。 您可以將 Jet 資料來源當做 OLE DB 資料來源。 不過，您對 `Open` 的呼叫需要兩個屬性集：一個用於 DBPROPSET_DBINIT，另一個用於 DBPROPSET_JETOLEDB_DBINIT，讓您可以設定 DBPROP_JETOLEDB_DATABASEPASSWORD。

[!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]

## <a name="cdatasourceopenfromfilename"></a><a name="openfromfilename"></a>CDataSource：： OpenFromFileName

從以使用者提供的檔名指定的檔案，開啟資料來源。

### <a name="syntax"></a>語法

```cpp
HRESULT OpenFromFileName(LPCOLESTR szFileName) throw();
```

#### <a name="parameters"></a>參數

*szFileName*<br/>
[in] 檔案的名稱，通常是資料來源連接 (.UDL) 檔案。

如需有關資料連結檔案（udl 檔案）的詳細資訊，請參閱 Windows SDK 中的[資料連結 API 總覽](/previous-versions/windows/desktop/ms718102(v=vs.85))。

### <a name="return-value"></a>傳回值

標準 HRESULT。

### <a name="remarks"></a>備註

這個方法會使用 oledb32.dll 中的服務元件開啟資料來源物件；此 DLL 包含服務元件功能的實作，例如資源集中化、自動交易登記等。 如需詳細資訊，請參閱 OLE DB 程式設計[人員指南](/previous-versions/windows/desktop/ms713643(v=vs.85))中的 OLE DB 參考。

## <a name="cdatasourceopenfrominitializationstring"></a><a name="openfrominitializationstring"></a>CDataSource：： OpenFromInitializationString

開啟由使用者提供的初始化字串所指定的資料來源。

### <a name="syntax"></a>語法

```cpp
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,
   bool fPromptForInfo= false) throw();
```

#### <a name="parameters"></a>參數

*szInitializationString*<br/>
在初始化字串。

*fPromptForInfo*<br/>
在如果這個引數設定為**true**，則 `OpenFromInitializationString` 會將 DBPROP_INIT_PROMPT 屬性設定為 DBPROMPT_COMPLETEREQUIRED，這會指定只有在需要更多資訊時才會提示使用者。 這適用于初始化字串指定需要密碼的資料庫，但該字串不包含密碼的情況。 嘗試連接到資料庫時，系統會提示使用者輸入密碼（或任何其他遺失的資訊）。

預設值為**false**，指定不會提示使用者（將 DBPROP_INIT_PROMPT 設定為 DBPROMPT_NOPROMPT）。

### <a name="return-value"></a>傳回值

標準 HRESULT。

### <a name="remarks"></a>備註

這個方法會使用 oledb32.dll 中的服務元件開啟資料來源物件；此 DLL 包含服務元件功能的實作，例如資源集中化、自動交易登記等。

## <a name="cdatasourceopenwithpromptfilename"></a><a name="openwithpromptfilename"></a>CDataSource：： OpenWithPromptFileName

此方法會以對話方塊提示使用者，然後使用使用者所指定的檔案開啟資料來源。

### <a name="syntax"></a>語法

```cpp
HRESULT OpenWithPromptFileName(HWND hWnd = GetActiveWindow(   ),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,
   LPCOLESTR szInitialDirectory = NULL) throw();
```

#### <a name="parameters"></a>參數

*hWnd*<br/>
[in] 做為對話方塊之父視窗的控制代碼。

*dwPromptOptions*<br/>
[in] 決定要顯示的定位程式對話方塊樣式。 請參閱 Msdasc.h 中的可能值。

*szInitialDirectory*<br/>
[in] 要顯示在定位器對話方塊中的初始目錄。

### <a name="return-value"></a>傳回值

標準 HRESULT。

### <a name="remarks"></a>備註

這個方法會使用 oledb32.dll 中的服務元件開啟資料來源物件；此 DLL 包含服務元件功能的實作，例如資源集中化、自動交易登記等。 如需詳細資訊，請參閱 OLE DB 程式設計[人員指南](/previous-versions/windows/desktop/ms713643(v=vs.85))中的 OLE DB 參考。

## <a name="cdatasourceopenwithservicecomponents"></a><a name="openwithservicecomponents"></a>CDataSource：： OpenWithServiceComponents

使用 oledb32.dll 中的服務元件來開啟資料來源物件。

### <a name="syntax"></a>語法

```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);

HRESULT OpenWithServiceComponents (LPCSTR szProgID,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);
```

#### <a name="parameters"></a>參數

*clsid*<br/>
在資料提供者的 `CLSID`。

*szProgID*<br/>
[in] 資料提供者的程式識別碼。

*傳入 ppropset*<br/>
在[DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))結構陣列的指標，其中包含要設定的屬性和值。 請參閱 Windows SDK 中 OLE DB 程式設計*人員參考*中的[屬性集和屬性群組](/previous-versions/windows/desktop/ms713696(v=vs.85))。 如果資料來源物件已初始化，屬性必須屬於資料來源屬性群組。 如果在*傳入 ppropset*中指定了相同的屬性一次以上，則使用的值是提供者特定的。 如果*ulPropSets*為零，則會忽略這個參數。

*ulPropSets*<br/>
在在*傳入 ppropset*引數中傳遞的[DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))結構數目。 如果這個值為零，則提供者會忽略*傳入 ppropset*。

### <a name="return-value"></a>傳回值

標準 HRESULT。

### <a name="remarks"></a>備註

這個方法會使用 oledb32.dll 中的服務元件開啟資料來源物件；此 DLL 包含服務元件功能的實作，例如資源集中化、自動交易登記等。 如需詳細資訊，請參閱 OLE DB 程式設計[人員指南](/previous-versions/windows/desktop/ms713643(v=vs.85))中的 OLE DB 參考。

## <a name="see-also"></a>另請參閱

[OLE DB 消費者範本](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 消費者範本參考](../../data/oledb/ole-db-consumer-templates-reference.md)
