---
title: CDaoTableDefInfo Structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoTableDefInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
caps.latest.revision: 13
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
ms.openlocfilehash: e0268fc3d7a88bf1290303c54cd27a14d1087360
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo Structure
The `CDaoTableDefInfo` structure contains information about a tabledef object defined for data access objects (DAO).  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoTableDefInfo  
{  
    CString m_strName;               // Primary  
    BOOL m_bUpdatable;               // Primary  
    long m_lAttributes;              // Primary  
    COleDateTime m_dateCreated;      // Secondary  
    COleDateTime m_dateLastUpdated;  // Secondary  
    CString m_strSrcTableName;       // Secondary  
    CString m_strConnect;            // Secondary  
    CString m_strValidationRule;     // All  
    CString m_strValidationText;     // All  
    long m_lRecordCount;             // All  
};  
```  
  
#### <a name="parameters"></a>Parameters  
 `m_strName`  
 Uniquely names the tabledef object. To retrieve the value of this property directly, call the tabledef object's [GetName](../../mfc/reference/cdaotabledef-class.md#getname) member function. For more information, see the topic "Name Property" in DAO Help.  
  
 `m_bUpdatable`  
 Indicates whether changes can be made to the table. The quick way to determine whether a table is updatable is to open a `CDaoTableDef` object for the table and call the object's [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) member function. `CanUpdate` always returns nonzero (**TRUE**) for a newly created tabledef object and 0 (**FALSE**) for an attached tabledef object. A new tabledef object can be appended only to a database for which the current user has write permission. If the table contains only nonupdatable fields, `CanUpdate` returns 0. When one or more fields are updatable, `CanUpdate` returns nonzero. You can edit only the updatable fields. For more information, see the topic "Updatable Property" in DAO Help.  
  
 `m_lAttributes`  
 Specifies characteristics of the table represented by the tabledef object. To retrieve the current attributes of a tabledef, call its [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) member function. The value returned can be a combination of these long constants (using the bitwise-OR (**&#124;**) operator):  
  
- **dbAttachExclusive** For databases that use the Microsoft Jet database engine, indicates the table is an attached table opened for exclusive use.  
  
- **dbAttachSavePWD** For databases that use the Microsoft Jet database engine, indicates that the user ID and password for the attached table are saved with the connection information.  
  
- **dbSystemObject** Indicates the table is a system table provided by the Microsoft Jet database engine. (Read-only.)  
  
- **dbHiddenObject** Indicates the table is a hidden table provided by the Microsoft Jet database engine (for temporary use). (Read-only.)  
  
- **dbAttachedTable** Indicates the table is an attached table from a non-ODBC database, such as a Paradox database.  
  
- **dbAttachedODBC** Indicates the table is an attached table from an ODBC database, such as Microsoft SQL Server.  
  
 `m_dateCreated`  
 The date and time the table was created. To directly retrieve the date the table was created, call the [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) member function of the `CDaoTableDef` object associated with the table. See Comments below for more information. For related information, see the topic "DateCreated, LastUpdated Properties" in DAO Help.  
  
 `m_dateLastUpdated`  
 The date and time of the most recent change made to the design of the table. To directly retrieve the date the table was last updated, call the [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) member function of the `CDaoTableDef` object associated with the table. See Comments below for more information. For related information, see the topic "DateCreated, LastUpdated Properties" in DAO Help.  
  
 *m_strSrcTableName*  
 Specifies the name of an attached table if any. To directly retrieve the source table name, call the [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) member function of the `CDaoTableDef` object associated with the table.  
  
 `m_strConnect`  
 Provides information about the source of an open database. You can check this property by calling the [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) member function of your `CDaoTableDef` object. For more information about connect strings, see `GetConnect`.  
  
 `m_strValidationRule`  
 A value that validates the data in tabledef fields as they are changed or added to a table. Validation is supported only for databases that use the Microsoft Jet database engine. To directly retrieve the validation rule, call the [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) member function of the `CDaoTableDef` object associated with the table. For related information, see the topic "ValidationRule Property" in DAO Help.  
  
 `m_strValidationText`  
 A value that specifies the text of the message that your application should display if the validation rule specified by the ValidationRule property is not satisfied. For related information, see the topic "ValidationText Property" in DAO Help.  
  
 *m_lRecordCount*  
 The number of records accessed in a tabledef object. This property setting is read-only. To directly retrieve the record count, call the [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) member function of the `CDaoTableDef` object. The documentation for `GetRecordCount` describes the record count further. Note that retrieving this count can be a time-consuming operation if the table contains many records.  
  
## <a name="remarks"></a>Remarks  
 The tabledef is an object of class [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). The references to Primary, Secondary, and All above indicate how the information is returned by the [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) member function in class `CDaoDatabase`.  
  
 Information retrieved by the [CDaoDatabase::GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) member function is stored in a `CDaoTableDefInfo` structure. Call the `GetTableDefInfo` member function of the `CDaoDatabase` object in whose TableDefs collection the tabledef object is stored. `CDaoTableDefInfo` also defines a `Dump` member function in debug builds. You can use `Dump` to dump the contents of a `CDaoTableDefInfo` object.  
  
 The date and time settings are derived from the computer on which the base table was created or last updated. In a multiuser environment, users should get these settings directly from the file server to avoid discrepancies in the DateCreated and LastUpdated property settings.  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>See Also  
 [Structures, Styles, Callbacks, and Message Maps](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)

