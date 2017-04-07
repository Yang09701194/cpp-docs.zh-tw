---
title: "norm_3 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::norm_3::get_z
- amp_short_vectors/Concurrency::graphics::norm_3::operator=
- amp_short_vectors/Concurrency::graphics::norm_3::r
- amp_short_vectors/Concurrency::graphics::norm_3::set_zyx
- amp_short_vectors/Concurrency::graphics::norm_3::xyz
- amp_short_vectors/Concurrency::graphics::norm_3::operator/=
- amp_short_vectors/Concurrency::graphics::norm_3::yz
- amp_short_vectors/Concurrency::graphics::norm_3::get_xyz
- amp_short_vectors/Concurrency::graphics::norm_3::br
- amp_short_vectors/Concurrency::graphics::norm_3::xy
- amp_short_vectors/Concurrency::graphics::norm_3::get_yzx
- amp_short_vectors/Concurrency::graphics::norm_3::set_xyz
- amp_short_vectors/Concurrency::graphics::norm_3::gr
- amp_short_vectors/Concurrency::graphics::norm_3::g
- amp_short_vectors/Concurrency::graphics::norm_3::set_yxz
- amp_short_vectors/Concurrency::graphics::norm_3::get_zyx
- amp_short_vectors/Concurrency::graphics::norm_3::get_y
- amp_short_vectors/Concurrency::graphics::norm_3::zx
- amp_short_vectors/Concurrency::graphics::norm_3::yzx
- amp_short_vectors/Concurrency::graphics::norm_3::gb
- amp_short_vectors/Concurrency::graphics::norm_3::xzy
- amp_short_vectors/Concurrency::graphics::norm_3::xz
- amp_short_vectors/Concurrency::graphics::norm_3::rb
- amp_short_vectors/Concurrency::graphics::norm_3::rgb
- amp_short_vectors/Concurrency::graphics::norm_3::b
- amp_short_vectors/Concurrency::graphics::norm_3::z
- amp_short_vectors/Concurrency::graphics::norm_3::operator*=
- amp_short_vectors/Concurrency::graphics::norm_3::operator+=
- amp_short_vectors/Concurrency::graphics::norm_3::get_zy
- amp_short_vectors/Concurrency::graphics::norm_3::get_xz
- amp_short_vectors/Concurrency::graphics::norm_3::gbr
- amp_short_vectors/Concurrency::graphics::norm_3::get_yz
- amp_short_vectors/Concurrency::graphics::norm_3::get_zx
- amp_short_vectors/Concurrency::graphics::norm_3::get_xzy
- amp_short_vectors/Concurrency::graphics::norm_3::set_xz
- amp_short_vectors/Concurrency::graphics::norm_3::set_xzy
- amp_short_vectors/Concurrency::graphics::norm_3::set_zy
- amp_short_vectors/Concurrency::graphics::norm_3::get_xy
- amp_short_vectors/Concurrency::graphics::norm_3::y
- amp_short_vectors/Concurrency::graphics::norm_3::yx
- amp_short_vectors/Concurrency::graphics::norm_3::rbg
- amp_short_vectors/Concurrency::graphics::norm_3::zxy
- amp_short_vectors/Concurrency::graphics::norm_3
- amp_short_vectors/Concurrency::graphics::norm_3::set_yz
- amp_short_vectors/Concurrency::graphics::norm_3::brg
- amp_short_vectors/Concurrency::graphics::norm_3::operator--
- amp_short_vectors/Concurrency::graphics::norm_3::yxz
- amp_short_vectors/Concurrency::graphics::norm_3::x
- amp_short_vectors/Concurrency::graphics::norm_3::set_x
- amp_short_vectors/Concurrency::graphics::norm_3::get_x
- amp_short_vectors/Concurrency::graphics::norm_3::get_yxz
- amp_short_vectors/Concurrency::graphics::norm_3::grb
- amp_short_vectors/Concurrency::graphics::norm_3::get_yx
- amp_short_vectors/Concurrency::graphics::norm_3::zy
- amp_short_vectors/Concurrency::graphics::norm_3::rg
- amp_short_vectors/Concurrency::graphics::norm_3::set_yzx
- amp_short_vectors/Concurrency::graphics::norm_3::operator-=
- amp_short_vectors/Concurrency::graphics::norm_3::bg
- amp_short_vectors/Concurrency::graphics::norm_3::operator++
- amp_short_vectors/Concurrency::graphics::norm_3::set_y
- amp_short_vectors/Concurrency::graphics::norm_3::zyx
- amp_short_vectors/Concurrency::graphics::norm_3::set_z
- amp_short_vectors/Concurrency::graphics::norm_3::operator-
- amp_short_vectors/Concurrency::graphics::norm_3::get_zxy
- amp_short_vectors/Concurrency::graphics::norm_3::set_xy
- amp_short_vectors/Concurrency::graphics::norm_3::set_zxy
- amp_short_vectors/Concurrency::graphics::norm_3::set_yx
- amp_short_vectors/Concurrency::graphics::norm_3::set_zx
- amp_short_vectors/Concurrency::graphics::norm_3::bgr
dev_langs:
- C++
ms.assetid: 17081060-14ce-477e-a71a-9801b0f1d9e4
caps.latest.revision: 9
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
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: ca5d8270f04240f99fa6735ea8235c2e077dfa01
ms.lasthandoff: 03/17/2017

---
# <a name="norm3-class"></a>norm_3 類別
代表三個一般數字的短向量。  
  
## <a name="syntax"></a>語法  
  
```  
class norm_3;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-typedefs"></a>公用 Typedefs  
  
|名稱|描述|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[norm_3 建構函式](#ctor)|多載。 預設建構函式，初始化為 0 的所有項目。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|norm_3::get_x||  
|norm_3::get_xy||  
|norm_3::get_xyz||  
|norm_3::get_xz||  
|norm_3::get_xzy||  
|norm_3::get_y||  
|norm_3::get_yx||  
|norm_3::get_yxz||  
|norm_3::get_yz||  
|norm_3::get_yzx||  
|norm_3::get_z||  
|norm_3::get_zx||  
|norm_3::get_zxy||  
|norm_3::get_zy||  
|norm_3::get_zyx||  
|norm_3:: ref_b||  
|norm_3:: ref_g||  
|norm_3:: ref_r||  
|norm_3:: ref_x||  
|norm_3:: ref_y||  
|norm_3:: ref_z||  
|norm_3::set_x||  
|norm_3::set_xy||  
|norm_3::set_xyz||  
|norm_3::set_xz||  
|norm_3::set_xzy||  
|norm_3::set_y||  
|norm_3::set_yx||  
|norm_3::set_yxz||  
|norm_3::set_yz||  
|norm_3::set_yzx||  
|norm_3::set_z||  
|norm_3::set_zx||  
|norm_3::set_zxy||  
|norm_3::set_zy||  
|norm_3::set_zyx||  
  
### <a name="public-operators"></a>公用運算子  
  
|名稱|描述|  
|----------|-----------------|  
|norm_3::operator-||  
|norm_3::operator-||  
|norm_3::operator * =||  
|norm_3::operator / =||  
|norm_3::operator + +||  
|norm_3::operator + =||  
|norm_3::operator =||  
|norm_3::operator =||  
  
### <a name="public-constants"></a>公用常數  
  
|名稱|描述|  
|----------|-----------------|  
|[大小常數](#size)||  
  
### <a name="public-data-members"></a>公用資料成員  
  
|名稱|描述|  
|----------|-----------------|  
|norm_3::b||  
|norm_3::bg||  
|norm_3::bgr||  
|norm_3::br||  
|norm_3::brg||  
|norm_3::g||  
|norm_3::gb||  
|norm_3::gbr||  
|norm_3::gr||  
|norm_3::grb||  
|norm_3::r||  
|norm_3::rb||  
|norm_3::rbg||  
|norm_3::rg||  
|norm_3::rgb||  
|norm_3::x||  
|norm_3::xy||  
|norm_3::xyz||  
|norm_3::xz||  
|norm_3::xzy||  
|norm_3::y||  
|norm_3::yx||  
|norm_3::yxz||  
|norm_3::yz||  
|norm_3::yzx||  
|norm_3::z||  
|norm_3::zx||  
|norm_3::zxy||  
|norm_3::zy||  
|norm_3::zyx||  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `norm_3`  
  
## <a name="requirements"></a>需求  
 **標頭︰** amp_short_vectors.h  
  
 **命名空間︰** concurrency:: graphics  

## <a name="ctor"></a>norm_3 建構函式
預設建構函式，初始化為 0 的所有項目。  
  
## <a name="syntax"></a>語法  
  
```  
norm_3() restrict(amp,cpu);  
norm_3(  
   norm _V0,  
   norm _V1,  
   norm _V2  
) restrict(amp,cpu);  
norm_3(  
   float _V0,  
   float _V1,  
   float _V2  
) restrict(amp,cpu);  
norm_3(  
   unorm _V0,  
   unorm _V1,  
   unorm _V2  
) restrict(amp,cpu);  
norm_3(  
   norm _V  
) restrict(amp,cpu);  
explicit norm_3(  
   float _V  
) restrict(amp,cpu);  
norm_3(  
   const norm_3& _Other  
) restrict(amp,cpu);  
explicit inline norm_3(  
   const uint_3& _Other  
) restrict(amp,cpu);  
explicit inline norm_3(  
   const int_3& _Other  
) restrict(amp,cpu);  
explicit inline norm_3(  
   const float_3& _Other  
) restrict(amp,cpu);  
explicit inline norm_3(  
   const unorm_3& _Other  
) restrict(amp,cpu);  
explicit inline norm_3(  
   const double_3& _Other  
) restrict(amp,cpu);  
```  
  
#### <a name="parameters"></a>參數  
 `_V0`  
 要初始化項目 0 的值。  
  
 `_V1`  
 要初始化項目 1 的值。  
  
 `_V2`  
 要初始化項目 2 的值。  
  
 `_V`  
 初始設定的值。  
  
 `_Other`  
 用來初始化物件。  
  
## <a name="a-namesize-size-constant"></a><a name="size">大小常數
### <a name="syntax"></a>語法  
  
```  
static const int size = 3;  
```   
 
## <a name="see-also"></a>另請參閱  
 [Concurrency::graphics 命名空間](concurrency-graphics-namespace.md)

