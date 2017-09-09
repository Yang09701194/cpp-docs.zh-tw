---
title: messages Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmes/std::messages
- locale/std::messages::char_type
- locale/std::messages::string_type
- locale/std::messages::close
- locale/std::messages::do_close
- locale/std::messages::do_get
- locale/std::messages::do_open
- locale/std::messages::get
- locale/std::messages::open
dev_langs:
- C++
helpviewer_keywords:
- std::messages [C++]
- std::messages [C++], char_type
- std::messages [C++], string_type
- std::messages [C++], close
- std::messages [C++], do_close
- std::messages [C++], do_get
- std::messages [C++], do_open
- std::messages [C++], get
- std::messages [C++], open
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: d81b70d987cbf9c6a08ea5db6338606531d5f0a5
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="messages-class"></a>messages Class
The template class describes an object that can serve as a locale facet to retrieve localized messages from a catalog of internationalized messages for a given locale.  
  
 Currently, while the messages class is implemented, there are no messages.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class CharType>  
class messages : public messages_base;
```  
  
#### <a name="parameters"></a>Parameters  
 `CharType`  
 The type used within a program to encode characters in a locale.  
  
## <a name="remarks"></a>Remarks  
 As with any locale facet, the static object ID has an initial stored value of zero. The first attempt to access its stored value stores a unique positive value in **id.**  
  
 This facet basically opens a catalog of messages defined in the base class messages_base, retrieves the information required, and closes the catalog.  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[messages](#messages)|The message facet constructor function.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#char_type)|A character type that is used display messages.|  
|[string_type](#string_type)|A type that describes a string of type `basic_string` containing characters of type `CharType`.|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[close](#close)|Closes the message catalog.|  
|[do_close](#do_close)|A virtual function called to lose the message catalog.|  
|[do_get](#do_get)|A virtual function called to retrieve the message catalog.|  
|[do_open](#do_open)|A virtual function called to open the message catalog.|  
|[get](#get)|Retrieves the message catalog.|  
|[open](#open)|Opens the message catalog.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>  messages::char_type  
 A character type that is used display messages.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for the template parameter **CharType**.  
  
##  <a name="close"></a>  messages::close  
 Closes the message catalog.  
  
```
void close(catalog _Catval) const;
```  
  
### <a name="parameters"></a>Parameters  
 `_Catval`  
 The catalog to be closed.  
  
### <a name="remarks"></a>Remarks  
 The member function calls [do_close](#do_close)(_ *Catval*).  
  
##  <a name="do_close"></a>  messages::do_close  
 A virtual function called to lose the message catalog.  
  
```
virtual void do_close(catalog _Catval) const;
```  
  
### <a name="parameters"></a>Parameters  
 `_Catval`  
 The catalog to be closed.  
  
### <a name="remarks"></a>Remarks  
 The protected member function closes the message catalog `_Catval`, which must have been opened by an earlier call to [do_open](#do_open).  
  
 *_Catval* must be obtained from a previously opened catalog that is not closed.  
  
### <a name="example"></a>Example  
  See the example for [close](#close), which calls `do_close`.  
  
##  <a name="do_get"></a>  messages::do_get  
 A virtual function called to retrieve the message catalog.  
  
```
virtual string_type do_get(
    catalog _Catval,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```  
  
### <a name="parameters"></a>Parameters  
 `_Catval`  
 The identification value specifying the message catalog to be searched.  
  
 `_Set`  
 The first identified used to locate a message in a message catalog.  
  
 `_Message`  
 The second identified used to locate a message in a message catalog.  
  
 `_Dfault`  
 The string to be returned on failure.  
  
### <a name="return-value"></a>Return Value  
 It returns a copy of `_Dfault` on failure. Otherwise, it returns a copy of the specified message sequence.  
  
### <a name="remarks"></a>Remarks  
 The protected member function tries to obtain a message sequence from the message catalog `_Catval`. It may make use of `_Set`, `_Message`, and `_Dfault` in doing so.  
  
### <a name="example"></a>Example  
  See the example for [get](#get), which calls `do_get`.  
  
##  <a name="do_open"></a>  messages::do_open  
 A virtual function called to open the message catalog.  
  
```
virtual catalog do_open(
    const string& _Catname,
    const locale& _Loc) const;
```  
  
### <a name="parameters"></a>Parameters  
 `_Catname`  
 The name of the catalog to be searched.  
  
 `_Loc`  
 The locale being searched for in the catalog.  
  
### <a name="return-value"></a>Return Value  
 It returns a value that compares less than zero on failure. Otherwise, the returned value can be used as the first argument on a later call to [get](#get).  
  
### <a name="remarks"></a>Remarks  
 The protected member function tries to open a message catalog whose name is `_Catname`. It may make use of the locale `_Loc` in doing so  
  
 The return value should be used as the argument on a later call to [close](#close).  
  
### <a name="example"></a>Example  
  See the example for [open](#open), which calls `do_open`.  
  
##  <a name="get"></a>  messages::get  
 Retrieves the message catalog.  
  
```
string_type get(
    catalog _CatVal,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```  
  
### <a name="parameters"></a>Parameters  
 `_Catval`  
 The identification value specifying the message catalog to be searched.  
  
 `_Set`  
 The first identified used to locate a message in a message catalog.  
  
 `_Message`  
 The second identified used to locate a message in a message catalog.  
  
 `_Dfault`  
 The string to be returned on failure.  
  
### <a name="return-value"></a>Return Value  
 It returns a copy of `_Dfault` on failure. Otherwise, it returns a copy of the specified message sequence.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_get](#do_get)( `_Catval`, `_Set`, `_Message`, `_Dfault`).  
  
##  <a name="messages"></a>  messages::messages  
 The message facet constructor function.  
  
```
explicit messages(
    size_t _Refs = 0);

protected: messages(
    const char* _Locname,
    size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Parameters  
 `_Refs`  
 Integer value used to specify the type of memory management for the object.  
  
 `_Locname`  
 The name of the locale.  
  
### <a name="remarks"></a>Remarks  
 The possible values for the `_Refs` parameter and their significance are:  
  
-   0: The lifetime of the object is managed by the locales that contain it.  
  
-   1: The lifetime of the object must be manually managed.  
  
-   \> 1: These values are not defined.  
  
 No direct examples are possible, because the destructor is protected.  
  
 The constructor initializes its base object with **locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`).  
  
##  <a name="open"></a>  messages::open  
 Opens the message catalog.  
  
```
catalog open(
    const string& _Catname,
    const locale& _Loc) const;
```  
  
### <a name="parameters"></a>Parameters  
 `_Catname`  
 The name of the catalog to be searched.  
  
 `_Loc`  
 The locale being searched for in the catalog.  
  
### <a name="return-value"></a>Return Value  
 It returns a value that compares less than zero on failure. Otherwise, the returned value can be used as the first argument on a later call to [get](#get).  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_open](#do_open)( `_Catname`, `_Loc`).  
  
##  <a name="string_type"></a>  messages::string_type  
 A type that describes a string of type `basic_string` containing characters of type **CharType**.  
  
```
typedef basic_string<CharType, Traits, Allocator> string_type;
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [basic_string](../standard-library/basic-string-class.md) whose objects can store copies of the message sequences.  
  
## <a name="see-also"></a>See Also  
 [\<locale>](../standard-library/locale.md)   
 [messages_base Class](../standard-library/messages-base-class.md)   
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)




