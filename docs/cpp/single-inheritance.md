---
title: 單一繼承
ms.date: 11/19/2018
helpviewer_keywords:
- single inheritance
- base classes [C++], indirect
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- derived classes [C++], single base class
- inheritance, single
ms.assetid: 1cb946ed-8b1b-4cf1-bde0-d9cecbfdc622
ms.openlocfilehash: 8fe141886fd5087b71484368c0f79d62238f7f22
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365604"
---
# <a name="single-inheritance"></a>單一繼承

在「單一繼承」(一種常見的繼承形式) 中，任何類別都只能有一個基底類別。 請考慮下圖中說明的關係。

![基本單&#45;繼承圖](../cpp/media/vc38xj1.gif "基本單&#45;繼承圖") <br/>
簡單的單一繼承圖形

請注意圖中從一般到特定的進展。 在大部分類別階層架構設計中，另一種常見的屬性是衍生類別，其與基底類別具有一種「種類」(kind of) 的關聯性。 在圖中，`Book` 是一種 `PrintedDocument`，而 `PaperbackBook` 是一種 `book`。

請注意圖中的其他項目：`Book` 同時為衍生類別 (來自 `PrintedDocument`) 和基底類別 (`PaperbackBook` 衍生自 `Book`)。 這種類別階層架構的基本架構宣告如下列範例所示：

```cpp
// deriv_SingleInheritance.cpp
// compile with: /LD
class PrintedDocument {};

// Book is derived from PrintedDocument.
class Book : public PrintedDocument {};

// PaperbackBook is derived from Book.
class PaperbackBook : public Book {};
```

`PrintedDocument` 被視為 `Book` 的「直接基底」類別，它是 `PaperbackBook` 的「間接基底」類別。 其中的差異是直接基底類別會出現在類別宣告的基底清單中，而間接基底則沒有。

每個類別的衍生基底類別都是在宣告衍生類別之前宣告。 它並不足以提供基底類別的向前參考宣告，且必須是完整的宣告。

在前面的範例中,使用存取指定者 **。** 公共、受保護和私有繼承的含義在[成員訪問控制中描述。](../cpp/member-access-control-cpp.md)

類別可做為許多特定類別的基底類別，如下圖所示。

![有向非循環圖](../cpp/media/vc38xj2.gif "有向非循環圖") <br/>
導向非循環圖的範例

上圖中 (稱為「導向非循環圖」或 "DAG") 的某些類別是多個衍生類別的基底類別。 不過，反向並不成立：其中只有一個指定衍生類別的直接基底類別。 此圖中描述了一個「單一繼承」結構。

> [!NOTE]
> 導向非循環圖不是唯一的單一繼承。 它們也可用來描述多重繼承圖形。

在繼承中，衍生類別包含基底類別的成員以及您加入的新成員。 因此，除非在衍生類別中重新定義這些成員，否則衍生類別可能會參考基底類別的成員。 當這些成員在衍生類別中重新定義時，可以使用範圍解析運算子 (`::`) 來參考直接或間接基底類別的成員。 請思考此範例：

```cpp
// deriv_SingleInheritance2.cpp
// compile with: /EHsc /c
#include <iostream>
using namespace std;
class Document {
public:
   char *Name;   // Document name.
   void PrintNameOf();   // Print name.
};

// Implementation of PrintNameOf function from class Document.
void Document::PrintNameOf() {
   cout << Name << endl;
}

class Book : public Document {
public:
   Book( char *name, long pagecount );
private:
   long  PageCount;
};

// Constructor from class Book.
Book::Book( char *name, long pagecount ) {
   Name = new char[ strlen( name ) + 1 ];
   strcpy_s( Name, strlen(Name), name );
   PageCount = pagecount;
};
```

請注意，`Book` 的建構函式 (即 `Book::Book`) 可以存取資料成員 `Name`。 在程式中可以建立及使用 `Book` 類型的物件，如下所示：

```cpp
//  Create a new object of type Book. This invokes the
//   constructor Book::Book.
Book LibraryBook( "Programming Windows, 2nd Ed", 944 );

...

//  Use PrintNameOf function inherited from class Document.
LibraryBook.PrintNameOf();
```

如上述範例中所示，類別成員和繼承的資料和函式的使用方式是相同的。 如果類別 `Book` 的實作呼叫 `PrintNameOf` 函式的重新實作，則只能使用範圍解析 (`Document`) 運算子呼叫屬於 `::` 類別中的函式：

```cpp
// deriv_SingleInheritance3.cpp
// compile with: /EHsc /LD
#include <iostream>
using namespace std;

class Document {
public:
   char *Name;          // Document name.
   void  PrintNameOf() {}  // Print name.
};

class Book : public Document {
   Book( char *name, long pagecount );
   void PrintNameOf();
   long  PageCount;
};

void Book::PrintNameOf() {
   cout << "Name of book: ";
   Document::PrintNameOf();
}
```

如果有一個可存取且明確的基底類別，衍生類別的指標和參考便可以隱含轉換為其基底類別的指標和參考。 下列程式碼使用指標示範這個概念 (相同原則適用於參考)：

```cpp
// deriv_SingleInheritance4.cpp
// compile with: /W3
struct Document {
   char *Name;
   void PrintNameOf() {}
};

class PaperbackBook : public Document {};

int main() {
   Document * DocLib[10];   // Library of ten documents.
   for (int i = 0 ; i < 5 ; i++)
      DocLib[i] = new Document;
   for (int i = 5 ; i < 10 ; i++)
      DocLib[i] = new PaperbackBook;
}
```

上述範例中建立了不同的類型。 不過，由於這些類型都是衍生自 `Document` 類別，所以會產生 `Document *` 的隱含轉換。 因此，`DocLib` 是一個「異質性清單」(在此清單中，並非所有物件都屬於相同類型)，其中包含不同類型的物件。

由於 `Document` 類別有一個 `PrintNameOf` 函式，它可以列印圖書館中每本書的名稱，不過，它可能會忽略文件的某些特定類型資訊 (`Book` 的頁面計數、`HelpFile` 的位元組數，等等)。

> [!NOTE]
> 強制基底類別實作如 `PrintNameOf` 等函式通常不是最好的設計。 [虛擬函數](../cpp/virtual-functions.md)提供其他設計備選方案。
