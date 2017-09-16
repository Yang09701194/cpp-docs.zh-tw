---
title: '&lt;regex&gt; typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex/std::cmatch
- regex/std::cregex_iterator
- regex/std::cregex_token_iterator
- regex/std::csub_match
- regex/std::regex
- regex/std::smatch
- regex/std::sregex_iterator
- regex/std::sregex_token_iterator
- regex/std::ssub_match
- regex/std::wcmatch
- regex/std::wcregex_iterator
- regex/std::wcregex_token_iterator
- regex/std::wcsub_match
- regex/std::wregex
- regex/std::wsmatch
- regex/std::wsregex_iterator
- regex/std::wsregex_token_iterator
- regex/std::wssub_match
dev_langs:
- C++
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 2424639155dc62847fef992a48b5c44d29b2f334
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ltregexgt-typedefs"></a>&lt;regex&gt; typedefs
||||  
|-|-|-|  
|[cmatch](#cmatch)|[cregex_iterator](#cregex_iterator)|[cregex_token_iterator](#cregex_token_iterator)|  
|[csub_match](#csub_match)|[regex](#regex)|[smatch](#smatch)|  
|[sregex_iterator](#sregex_iterator)|[sregex_token_iterator](#sregex_token_iterator)|[ssub_match](#ssub_match)|  
|[wcmatch](#wcmatch)|[wcregex_iterator](#wcregex_iterator)|[wcregex_token_iterator](#wcregex_token_iterator)|  
|[wcsub_match](#wcsub_match)|[wregex](#wregex)|[wsmatch](#wsmatch)|  
|[wsregex_iterator](#wsregex_iterator)|[wsregex_token_iterator](#wsregex_token_iterator)|[wssub_match](#wssub_match)|  
  
##  <a name="cmatch"></a>  cmatch Typedef  
 Type definition for char match_results.  
  
```  
typedef match_results<const char*> cmatch;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [match_results Class](../standard-library/match-results-class.md) for iterators of type `const char*`.  
  
##  <a name="cregex_iterator"></a>  cregex_iterator Typedef  
 Type definition for char regex_iterator.  
  
```  
typedef regex_iterator<const char*> cregex_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [regex_iterator Class](../standard-library/regex-iterator-class.md) for iterators of type `const char*`.  
  
##  <a name="cregex_token_iterator"></a>  cregex_token_iterator Typedef  
 Type definition for char regex_token_iterator  
  
```  
typedef regex_token_iterator<const char*> cregex_token_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [regex_token_iterator Class](../standard-library/regex-token-iterator-class.md) for iterators of type `const char*`.  
  
##  <a name="csub_match"></a>  csub_match Typedef  
 Type definition for char sub_match.  
  
```  
typedef sub_match<const char*> csub_match;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [sub_match Class](../standard-library/sub-match-class.md) for iterators of type `const char*`.  
  
##  <a name="regex"></a>  regex Typedef  
 Type definition for char basic_regex.  
  
```  
typedef basic_regex<char> regex;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [basic_regex Class](../standard-library/basic-regex-class.md) for elements of type `char`.  
  
> [!NOTE]
>  High-bit characters will have unpredictable results with `regex`. Values outside the range of 0 to 127 may result in undefined behavior.  
  
##  <a name="smatch"></a>  smatch Typedef  
 Type definition for string match_results.  
  
```  
typedef match_results<string::const_iterator> smatch;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [match_results Class](../standard-library/match-results-class.md) for iterators of type `string::const_iterator`.  
  
##  <a name="sregex_iterator"></a>  sregex_iterator Typedef  
 Type definition for string regex_iterator.  
  
```  
typedef regex_iterator<string::const_iterator> sregex_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [regex_iterator Class](../standard-library/regex-iterator-class.md) for iterators of type `string::const_iterator`.  
  
##  <a name="sregex_token_iterator"></a>  sregex_token_iterator Typedef  
 Type definition for string regex_token_iterator.  
  
```  
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [regex_token_iterator Class](../standard-library/regex-token-iterator-class.md) for iterators of type `string::const_iterator`.  
  
##  <a name="ssub_match"></a>  ssub_match Typedef  
 Type definition for string sub_match.  
  
```  
typedef sub_match<string::const_iterator> ssub_match;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [sub_match Class](../standard-library/sub-match-class.md) for iterators of type `string::const_iterator`.  
  
##  <a name="wcmatch"></a>  wcmatch Typedef  
 Type definition for wchar_t match_results.  
  
```  
typedef match_results<const wchar_t *> wcmatch;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [match_results Class](../standard-library/match-results-class.md) for iterators of type `const wchar_t*`.  
  
##  <a name="wcregex_iterator"></a>  wcregex_iterator Typedef  
 Type definition for wchar_t regex_iterator.  
  
```  
typedef regex_iterator<const wchar_t*> wcregex_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [regex_iterator Class](../standard-library/regex-iterator-class.md) for iterators of type `const wchar_t*`.  
  
##  <a name="wcregex_token_iterator"></a>  wcregex_token_iterator Typedef  
 Type definition for wchar_t regex_token_iterator.  
  
```  
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [regex_token_iterator Class](../standard-library/regex-token-iterator-class.md) for iterators of type `const wchar_t*`.  
  
##  <a name="wcsub_match"></a>  wcsub_match Typedef  
 Type definition for wchar_t sub_match.  
  
```  
typedef sub_match<const wchar_t*> wcsub_match;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [sub_match Class](../standard-library/sub-match-class.md) for iterators of type `const wchar_t*`.  
  
##  <a name="wregex"></a>  wregex Typedef  
 Type definition for wchar_t basic_regex.  
  
```  
typedef basic_regex<wchar_t> wregex;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [basic_regex Class](../standard-library/basic-regex-class.md) for elements of type `wchar_t`.  
  
##  <a name="wsmatch"></a>  wsmatch Typedef  
 Type definition for wstring match_results.  
  
```  
typedef match_results<wstring::const_iterator> wsmatch;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [match_results Class](../standard-library/match-results-class.md) for iterators of type `wstring::const_iterator`.  
  
##  <a name="wsregex_iterator"></a>  wsregex_iterator Typedef  
 Type definition for wstring regex_iterator.  
  
```  
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [regex_iterator Class](../standard-library/regex-iterator-class.md) for iterators of type `wstring::const_iterator`.  
  
##  <a name="wsregex_token_iterator"></a>  wsregex_token_iterator Typedef  
 Type definition for wstring regex_token_iterator.  
  
```  
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [regex_token_iterator Class](../standard-library/regex-token-iterator-class.md) for iterators of type `wstring::const_iterator`.  
  
##  <a name="wssub_match"></a>  wssub_match Typedef  
 Type definition for wstring sub_match.  
  
```  
typedef sub_match<wstring::const_iterator> wssub_match;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [sub_match Class](../standard-library/sub-match-class.md) for iterators of type `wstring::const_iterator`.  
  
## <a name="see-also"></a>See Also  
[\<regex>](../standard-library/regex.md)  
[regex_constants Class](../standard-library/regex-constants-class.md)  
[regex_error Class](../standard-library/regex-error-class.md)  
[\<regex> functions](../standard-library/regex-functions.md)  
[regex_iterator Class](../standard-library/regex-iterator-class.md)  
[\<regex> operators](../standard-library/regex-operators.md)  
[regex_token_iterator Class](../standard-library/regex-token-iterator-class.md)  
[regex_traits Class](../standard-library/regex-traits-class.md)  

