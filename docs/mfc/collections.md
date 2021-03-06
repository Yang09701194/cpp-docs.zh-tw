---
title: 集合
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, collections
- arrays [MFC], classes
- MFC collection classes
- shapes, collection
- collection classes [MFC], MFC
- collections, about collections
- array templates [MFC]
- collection classes [MFC], template-based
- collection classes [MFC], about collection classes
- collection classes [MFC], maps
- collection classes [MFC], arrays
- shapes
- collection classes [MFC], lists
- collection classes [MFC], shapes
ms.assetid: 02586e4c-851d-41d0-a722-feb11c17c74c
ms.openlocfilehash: 3fba3a3c6cd3fecbda7f46575b1d72c450c44019
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361861"
---
# <a name="collections"></a>集合

MFC 程式庫提供集合類別管理物件群組。 這些類別有兩種類型：

- [從 C++ 樣板建立的集合類別](#_core_the_template_based_collection_classes)

- [不是從樣板建立的集合類別](#_core_the_collection_classes_not_based_on_templates)

> [!NOTE]
> 如果您的程式碼已經使用非樣板集合類別，則可以繼續使用它們。 如果您為您的資料類型撰寫新的類型安全集合類別，建議您使用較新的樣板型類別。

## <a name="collection-shapes"></a><a name="_core_collection_shapes"></a>集合元件

集合類別是依其圖形與其項目的類型來區別。 圖形是指依照集合來組織和儲存物件的方式。 MFC 提供三個基本集合圖形：清單、陣列和對應 (也稱為字典)。 您可以選擇最適合您的特定程式設計問題的集合圖形。

本主題稍後將簡短說明所提供三種集合圖形的各個圖形。 要比較元件的特徵,以説明您確定哪個最適合您的程式,請參閱[選擇集合類的建議](../mfc/recommendations-for-choosing-a-collection-class.md)。

- 清單

   清單類別提供經過排序非索引式的項目清單，實作為雙向連結串列。 清單中有「開頭」與「結尾」，從開頭或結尾加入或移除項目，或者從中間插入或刪除項目，都非常快速。

- Array

   陣列類別提供動態調整大小、經過排序且整數索引式的物件陣列。

- 對應 (也稱為字典)

   對應是將金鑰物件與值物件建立關聯的集合。

## <a name="the-template-based-collection-classes"></a><a name="_core_the_template_based_collection_classes"></a>基於樣本的集合類

實作包含任何類型物件的類型安全集合的最簡單方法，是使用其中一個 MFC 樣板型類別。 有關這些類的範例,請參閱 MFC 範例[COLLECT](../overview/visual-cpp-samples.md)。

下表列出的是 MFC 樣板型集合類別。

### <a name="collection-template-classes"></a>集合樣板類別

|集合內容|陣列|清單|地圖|
|-------------------------|------------|-----------|----------|
|任何類型物件的集合|`CArray`|`CList`|`CMap`|
|指向任何類型物件的指標集合|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|

## <a name="the-collection-classes-not-based-on-templates"></a><a name="_core_the_collection_classes_not_based_on_templates"></a>不基於樣本的集合類

如果您的應用程式已經使用 MFC 非樣板類別，可以繼續使用它們。 不過，對於新的集合，建議您使用樣板型類別。 下表列出的不是根據樣板的 MFC 集合類別。

### <a name="nontemplate-collection-classes"></a>非樣板集合類別

|陣列|清單|地圖|
|------------|-----------|----------|
|`CObArray`|`CObList`|`CMapPtrToWord`|
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|
|`CDWordArray`|`CStringList`|`CMapStringToOb`|
|`CPtrArray`||`CMapStringToPtr`|
|`CStringArray`||`CMapStringToString`|
|`CWordArray`||`CMapWordToOb`|
|`CUIntArray`||`CMapWordToPtr`|

[選擇集合類別的類別的名稱表](../mfc/recommendations-for-choosing-a-collection-class.md)的特徵根據這些特徵(形狀以外的)描述 MFC 集合類:

- 類別會使用 C++ 樣板與否

- 儲存在集合中的項目是否可序列化

- 儲存在集合中的項目是否可傾印以進行診斷

- 集合是否為安全類型

### <a name="what-do-you-want-to-do"></a>你想做什麼

#### <a name="general-collection-class-tasks"></a>一般集合類別工作

- [選擇集合類別的建議](../mfc/recommendations-for-choosing-a-collection-class.md)

- [如何：建立型別安全集合](../mfc/how-to-make-a-type-safe-collection.md)

- [建立堆疊和佇列集合](../mfc/creating-stack-and-queue-collections.md)

- [CArray::新增](../mfc/reference/carray-class.md#add)

#### <a name="template-based-collection-class-tasks"></a>樣板型集合類別工作

- [樣板架構類別](../mfc/template-based-classes.md)

#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>存取集合的成員 (樣板型或非樣板型)

- [存取集合的所有成員](../mfc/accessing-all-members-of-a-collection.md)

- [刪除 CObject 集合中的所有物件](../mfc/deleting-all-objects-in-a-cobject-collection.md)

## <a name="see-also"></a>另請參閱

[概念](../mfc/mfc-concepts.md)<br/>
[一般 MFC 主題](../mfc/general-mfc-topics.md)
