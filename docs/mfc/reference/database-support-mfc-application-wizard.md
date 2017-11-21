---
title: "資料庫支援，MFC 應用程式精靈 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfc.exe.database
dev_langs: C++
helpviewer_keywords: MFC Application Wizard, database support
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 875df8f8205d132cf6bcafe536c221876a5e3e51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="database-support-mfc-application-wizard"></a>MFC 應用程式精靈、資料庫支援
此頁面提供選項，可讓您指定的資料庫層級支援 （再加上資料來源，如有必要） 為您的專案。  
  
 **資料庫支援**  
 設定專案的資料庫支援的層級。  
  
|選項|說明|  
|------------|-----------------|  
|**無**|不提供資料庫支援。 這是預設選項。|  
|**僅限標頭檔**|提供您的應用程式的資料庫支援的基本層級。 如果您選取下的 ODBC 支援**用戶端類型**，MFC 應用程式精靈包含在專案中的標頭檔 AFXDB。H. 它會將連結程式庫，但不會建立任何資料庫特有類別。 您可以稍後再建立資料錄集，並用來檢查和更新記錄。 如果您選取 OLE DB 支援下的**用戶端類型**，會包含下列標頭檔： ATLBASE。H AFXOLEDB。H ATLPLUS。H|  
|**未提供檔案支援的資料庫檢視**|包含資料庫標頭檔、 連結程式庫、 資料錄檢視和資料錄集。 (僅適用於應用程式與**文件/檢視架構支援**選項中選取[應用程式類型](../../mfc/reference/application-type-mfc-application-wizard.md)頁面。)這個選項會包含文件支援，但沒有序列化支援。 如果您選擇要包含資料庫檢視，您必須指定資料的來源。|  
|**提供檔案支援的資料庫檢視**|包含資料庫標頭檔、 連結程式庫、 資料錄檢視和資料錄集。 (僅適用於應用程式與**文件/檢視架構支援**選項中選取**應用程式類型**頁面。)此選項支援文件序列化，您可以使用，例如，若要更新的使用者設定檔。 資料庫應用程式通常會操作針對每一筆記錄，而非每個檔案，因此不需要序列化。 不過，您可能必須進行序列化的特殊使用。 如果您選擇要包含資料庫檢視，您必須指定資料的來源。|  
  
> [!NOTE]
>  下**資料庫支援**，如果您選取任何**Database 未提供檔案支援檢視**或**資料庫檔案支援的檢視**，檢視類別的衍生不同，取決於在您**用戶端類型**選取項目，如下所示：  
  
-   如果您選取**ODBC**下**用戶端類型**，則應用程式的檢視類別衍生自[CRecordView](../../mfc/reference/crecordview-class.md)。 這個類別相關聯[CRecordset](../../mfc/reference/crecordset-class.md)-衍生的類別，MFC 應用程式精靈也會為您建立。 此選項可讓您的表單架構應用程式中的資料錄檢視用來檢視及更新透過其資料錄集的記錄。  
  
-   如果您選取**OLE DB**下**用戶端類型**，然後檢視類別衍生自[COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)，和其相關聯[CTable](../../data/oledb/ctable-class.md)或[CCommand](../../data/oledb/ccommand-class.md)-衍生的類別。  
  
 **用戶端類型**  
 表示專案是否使用 OLE DB 或 ODBC 類別。  
  
|選項|說明|  
|------------|-----------------|  
|**OLE DB**|選取此選項時，按一下**資料來源**按鈕可叫用**資料連結屬性**精靈來協助您建立的 OLE DB 資料來源的連接。|  
|**ODBC**|選取此選項時，按一下**資料來源**按鈕可叫用**選取資料來源**精靈來協助您建立 ODBC 資料來源的連接。|  
  
 **資料來源**  
 按一下**資料來源**按鈕，以設定資料來源以使用指定的驅動程式或提供者和資料庫。 如果您選取 OLE DB 中**用戶端類型**選項，此按鈕會顯示**資料連結屬性** 對話方塊。 如果您選取中的 ODBC**用戶端類型**選項，這個按鈕可以**選取資料來源** 對話方塊。 只有當您選擇要在您的應用程式中包含資料庫檢視時，才使用此選項。  
  
|選項|說明|  
|------------|-----------------|  
|**資料連結屬性**(OLE DB)|建立使用指定的 OLE DB 提供者的指定的資料來源。 您必須指定 OLE DB 提供者、 資料、 資料來源、 登入識別碼，以及 （選擇性） 密碼的位置。 如需有關此對話方塊的詳細資訊，請參閱**資料來源**中[ATL OLE DB 消費者精靈](../../atl/reference/atl-ole-db-consumer-wizard.md)。|  
|**選取資料來源**(ODBC)|建立指定的資料來源，使用指定的 ODBC 驅動程式。 您必須選取要選擇資料來源的資料表的資料來源名稱。 精靈將資料表的所有資料行繫結至成員變數的`CRecordset`-衍生的類別。 如需有關此對話方塊的詳細資訊，請參閱**資料來源**中[MFC ODBC 消費者精靈](../../mfc/reference/mfc-odbc-consumer-wizard.md)。|  
  
> [!NOTE]
>  在舊版中，Shift 按一下**資料來源**按鈕開啟 [開啟檔案] 對話方塊，讓您選取的資料連結 (.udl) 檔案。 不再支援此功能。  
  
 **產生屬性化的資料庫類別**  
 OLE DB 用戶端只可以使用。 指定是否在產生的專案資料庫類別使用屬性。  
  
 **繫結的所有資料行**  
 ODBC 用戶端只可以使用。 指定選取之資料表中的所有資料行是否繫結。 如果您選取此方塊時，繫結的所有資料行;如果您未選取此方塊，沒有資料行繫結，以及您必須將其繫結以手動方式在資料錄集類別。  
  
 **Type**  
 ODBC 用戶端只可以使用。 指定資料錄集是否為動態集或快照集下, 表中所述。  
  
|選項|說明|  
|------------|-----------------|  
|**動態集**|指定資料錄集是動態集。 動態集是提供查詢的資料庫資料的索引檢視表查詢的結果。 動態集快取的整數索引原始資料，並因此提供了一效能中取得快照集。 索引會指向直接每一筆記錄找到為查詢的結果，並指出是否要清除記錄。 您也在查詢記錄的更新資訊的存取。|  
|快照|指定資料錄集是快照集。 快照是查詢的結果，而且時間是在某個時間點的資料庫檢視。 快取查詢結果所發現的所有記錄，因此不會看到原始記錄的任何變更。|  
  
## <a name="see-also"></a>另請參閱  
 [MFC 應用程式精靈](../../mfc/reference/mfc-application-wizard.md)