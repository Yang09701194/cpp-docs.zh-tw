---
title: 新增成員函式
ms.date: 11/09/2018
f1_keywords:
- vc.codewiz.classes.member.function
- vc.codewiz.function.overview
helpviewer_keywords:
- member functions, adding to classes
- classes [C++], adding members
- add member function wizard [C++]
ms.assetid: 55b25ddb-541d-44ed-957c-974ef91cfc85
ms.openlocfilehash: 1cd7abbbc43ae56861b3b83451b41933b8b0b4f0
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693408"
---
# <a name="add-a-member-function"></a>新增成員函式

在 [類別檢視] 中，您可以將成員函式新增至任何類別之中。 當您這樣做，宣告會加入至標頭檔，而 Stub 成員函式主體會加入至該類別的實作檔 (可以修改這個檔案)。

**將成員函式新增至類別：**

1. 在**類別檢視**中，展開專案節點，顯示專案中的類別。 (若要開啟 [類別檢視]，請在功能表列上，選擇 [檢視]、[類別檢視])。

1. 開啟要新增成員函式之類別的捷徑功能表，然後選取 [新增]、[新增函式]。

1. 提供成員函式的詳細資訊。 如需詳細資訊，請參閱[新增成員函式精靈](#add-member-function-wizard)。

1. 選擇 [完成] 按鈕以產生成員函式程式碼。

## <a name="in-this-section"></a>本節內容

- [新增成員函式精靈](#add-member-function-wizard)

## <a name="add-member-function-wizard"></a>新增成員函式精靈

此精靈可將成員函式宣告新增至標頭檔。 它還會將虛設常式成員函式實作新增至所選取類別的實作檔。

一旦您使用精靈來新增成員函式，即可在開發環境中編輯程式碼。

- **傳回類型**

  設定您所要新增成員函式的傳回型別。 您可以提供自己的傳回型別，或從可用型別清單中選取。 如需這些類型的資訊，請參閱[基本類型](../cpp/fundamental-types-cpp.md)。

  | | | |
  |---|---|---|
  | `char` | `int` | `unsigned int` |
  | `double` | `long` | `unsigned long` |
  | `float` | `short` | `void` |
  | `HRESULT` | `unsigned char` | |

- **函式名稱**

  設定您所要新增成員函式的名稱。

- **參數型別**

  如果成員函式有參數，請設定您要為成員函式新增的參數類型。 您可以提供自己的參數型別，或從可用型別清單中選取。

  | | | |
  |---|---|---|
  | `char` | `int` | `unsigned char` |
  | `double` | `long` | `unsigned int` |
  | `float` | `short` | `unsigned long` |

- **參數名稱**

  如果成員函式有參數，請設定您要為成員函式新增的參數名稱。

- **參數清單**

  顯示您已新增至成員函式的參數清單。 若要將參數新增至清單，請在 [參數類型] 和 [參數名稱] 方塊中提供類型和名稱，然後按一下 [新增]。 若要從清單移除參數，請選取參數，然後選取 [移除]。

- **存取權**

  設定成員函式的存取權。 存取修飾詞是指定其他類別對成員函式所具有之存取權的關鍵字。 如需指定存取權的詳細資訊，請參閱[成員存取控制](../cpp/member-access-control-cpp.md)。 成員函式存取層級預設為 `public`。

  - [public](../cpp/public-cpp.md)
  - [protected](../cpp/protected-cpp.md)
  - [private](../cpp/private-cpp.md)

  請檢查新的成員函式是靜態還是虛擬，以及它是內嵌還是純虛擬函式。 如果您將成員函式設為純虛擬函式，則會選取 [虛擬] 核取方塊，且 [內嵌] 核取方塊會變成無法使用。 預設為非靜態、非虛擬成員函式。

  | 選項 | 描述 |
  |--------|-------------|
  | [Static](../cpp/storage-classes-cpp.md) |  指定函式的作用就像全域，而且可以在類別外部呼叫，即使沒有類別具現化也一樣。 成員函式無法存取非靜態成員。 指定為 `Static` 的成員函式不可為虛擬。 |
  | [虛擬](../cpp/virtual-cpp.md) | 不論呼叫成員函式時使用的運算式為何，都可確定針對物件呼叫正確的成員函式。 指定為 `Virtual` 的成員函式不可為靜態。 |
  | **純虛擬** | 表示未針對所宣告的虛擬成員函式提供任何實作。 **純虛擬**只能在虛擬成員函式上指定。 至少包含一個純虛擬成員函式的類別會被視為抽象類別。 衍生自抽象類別的類別必須實作純虛擬成員函式，否則這些類別也是抽象類別。 |
  | [內嵌](../cpp/inline-functions-cpp.md) | 指示編譯器插入份成員函式主體複本至呼叫成員函式的每個地方。 指定為**內嵌**的成員函式不可為純虛擬。 |

- **.cpp 檔**

  設定寫入虛設常式成員函式實作的檔案位置。 根據預設，它會寫入至新增成員函式目標類別的 .cpp 檔案。 選取省略符號按鈕，以變更檔案名稱。 成員函式實作會新增至所選取檔案的內容。

- **註解**

  提供成員函式之標頭檔中的註解。

- **函式簽章**

  當您選取 [完成] 時，從程式碼逐字顯示成員函式。 您無法編輯此方塊中的文字。 若要變更成員函式，請變更精靈中的適當方塊。
