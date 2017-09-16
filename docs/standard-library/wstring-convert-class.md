---
title: wstring_convert Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- wstring/stdext::cvt::wstring_convert
- locale/std::wstring_convert::byte_string
- locale/std::wstring_convert::wide_string
- locale/std::wstring_convert::state_type
- locale/std::wstring_convert::int_type
- locale/std::wstring_convert::from_bytes
- locale/std::wstring_convert::to_bytes
- locale/std::wstring_convert::converted
- locale/std::wstring_convert::state
dev_langs:
- C++
helpviewer_keywords:
- stdext::cvt [C++], wstring_convert
- std::wstring_convert [C++], byte_string
- std::wstring_convert [C++], wide_string
- std::wstring_convert [C++], state_type
- std::wstring_convert [C++], int_type
- std::wstring_convert [C++], from_bytes
- std::wstring_convert [C++], to_bytes
- std::wstring_convert [C++], converted
- std::wstring_convert [C++], state
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
caps.latest.revision: 25
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
ms.openlocfilehash: 5478dc495a093d40297d23f1ba6d988049670d0c
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="wstringconvert-class"></a>wstring_convert Class
The template class `wstring_convert` performs conversions between a wide string and a byte string.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Codecvt, class Elem = wchar_t>
class wstring_convert
```  
  
#### <a name="parameters"></a>Parameters  
 Codecvt  
 The [locale](../standard-library/locale-class.md) facet that represents the conversion object.  
  
 Elem  
 The wide-character element type.  
  
## <a name="remarks"></a>Remarks  
 The template class describes an object that controls conversions between wide string objects of class `std::basic_string<Elem>` and byte string objects of class `std::basic_string<char>` (also known as `std::string`). The template class defines the types `wide_string` and `byte_string` as synonyms for these two types. Conversion between a sequence of `Elem` values (stored in a `wide_string` object) and multibyte sequences (stored in a `byte_string` object) is performed by an object of class `Codecvt<Elem, char, std::mbstate_t>`, which meets the requirements of the standard code-conversion facet `std::codecvt<Elem, char, std::mbstate_t>`.  
  
 An object of this template class stores:  
  
-   A byte string to display on errors  
  
-   A wide string to display on errors  
  
-   A pointer to the allocated conversion object (which is freed when the wbuffer_convert object is destroyed)  
  
-   A conversion state object of type [state_type](#state_type)  
  
-   A conversion count  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[wstring_convert](#wstring_convert)|Constructs an object of type `wstring_convert`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[byte_string](#byte_string)|A type that represents a byte string.|  
|[wide_string](#wide_string)|A type that represents a wide string.|  
|[state_type](#state_type)|A type that represents the conversion state.|  
|[int_type](#int_type)|A type that represents an integer.|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[from_bytes](#from_bytes)|Converts a byte string to a wide string.|  
|[to_bytes](#to_bytes)|Converts a wide string to a byte string.|  
|[converted](#converted)|Returns the number of successful conversions.|  
|[state](#state)|Returns an object representing the state of the conversion.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
##  <a name="byte_string"></a>  wstring_convert::byte_string  
 A type that represents a byte string.  
  
```
typedef std::basic_string<char> byte_string;
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for `std::basic_string<char>`.  
  
##  <a name="converted"></a>  wstring_convert::converted  
 Returns the number of successful conversions.  
  
```
size_t converted() const;
```  
  
### <a name="return-value"></a>Return Value  
 The number of successful conversions.  
  
### <a name="remarks"></a>Remarks  
 The number of successful conversions is stored in the conversion count object.  
  
##  <a name="from_bytes"></a>  wstring_convert::from_bytes  
 Converts a byte string to a wide string.  
  
```
wide_string from_bytes(char Byte);
wide_string from_bytes(const char* ptr);
wide_string from_bytes(const byte_string& Bstr);
wide_string from_bytes(const char* first, const char* last);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`Byte`|The single-element byte sequence to be converted.|  
|`ptr`|The C-style, null-terminated sequence of characters to be converted.|  
|`Bstr`|The [byte_string](#byte_string) to be converted.|  
|`first`|The first character in a range of characters to be converted.|  
|`last`|The last character in a range of characters to be converted.|  
  
### <a name="return-value"></a>Return Value  
 A wide string object resulting from the conversion.  
  
### <a name="remarks"></a>Remarks  
 If the [conversion state](../standard-library/wstring-convert-class.md) object was `not` constructed with an explicit value, it is set to its default value (the initial conversion state) before the conversion begins. Otherwise it is left unchanged.  
  
 The number of input elements successfully converted is stored in the conversion count object. If no conversion error occurs, the member function returns the converted wide string. Otherwise, if the object was constructed with an initializer for the wide-string error message, the member function returns the wide-string error message object. Otherwise, the member function throws an object of class [range_error](../standard-library/range-error-class.md).  
  
##  <a name="int_type"></a>  wstring_convert::int_type  
 A type that represents an integer.  
  
```
typedef typename wide_string::traits_type::int_type int_type;
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for `wide_string::traits_type::int_type`.  
  
##  <a name="state"></a>  wstring_convert::state  
 Returns an object representing the state of the conversion.  
  
```
state_type state() const;
```  
  
### <a name="return-value"></a>Return Value  
 The [conversion state](../standard-library/wstring-convert-class.md) object that represents the state of the conversion.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="state_type"></a>  wstring_convert::state_type  
 A type that represents the conversion state.  
  
```
typedef typename Codecvt::state_type state_type;
```  
  
### <a name="remarks"></a>Remarks  
 The type describes an object that can represent a conversion state. The type is a synonym for `Codecvt::state_type`.  
  
##  <a name="to_bytes"></a>  wstring_convert::to_bytes  
 Converts a wide string to a byte string.  
  
```
byte_string to_bytes(Elem Char);
byte_string to_bytes(const Elem* Wptr);
byte_string to_bytes(const wide_string& Wstr);
byte_string to_bytes(const Elem* first, const Elem* last);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`Char`|The wide character to be converted.|  
|`Wptr`|The C-style, null-terminated sequence, beginning at `wptr`, to be converted.|  
|`Wstr`|The [wide_string](#wide_string) to be converted.|  
|`first`|The first element in a range of elements to be converted.|  
|`last`|The last element in a range of elements to be converted.|  
  
### <a name="remarks"></a>Remarks  
 If the [conversion state](../standard-library/wstring-convert-class.md) object was `not` constructed with an explicit value, it is set to its default value (the initial conversion state) before the conversion begins. Otherwise it is left unchanged.  
  
 The number of input elements successfully converted is stored in the conversion count object. If no conversion error occurs, the member function returns the converted byte string. Otherwise, if the object was constructed with an initializer for the byte-string error message, the member function returns the byte-string error message object. Otherwise, the member function throws an object of class [range_error](../standard-library/range-error-class.md).  
  
##  <a name="wide_string"></a>  wstring_convert::wide_string  
 A type that represents a wide string.  
  
```
typedef std::basic_string<Elem> wide_string;
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for `std::basic_string<Elem>`.  
  
##  <a name="wstring_convert"></a>  wstring_convert::wstring_convert  
 Constructs an object of type `wstring_convert`.  
  
```
wstring_convert(Codecvt *Pcvt = new Codecvt);
wstring_convert(Codecvt *Pcvt, state_type _State);
wstring_convert(const byte_string& _Berr, const wide_string& Werr = wide_string());
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`*Pcvt`|The object of type `Codecvt` to perform the conversion.|  
|`_State`|The object of type [state_type](#state_type) representing the conversion state.|  
|`_Berr`|The [byte_string](#byte_string) to display on errors.|  
|`Werr`|The [wide_string](#wide_string) to display on errors.|  
  
### <a name="remarks"></a>Remarks  
 The first constructor stores *Pcvt_arg* in the [conversion object](../standard-library/wstring-convert-class.md)

