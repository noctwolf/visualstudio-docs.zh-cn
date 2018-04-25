---
title: 查看类型和关系（类设计器）| Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.CannotShowBaseType
helpviewer_keywords:
- class diagrams
- types [Visual Studio], visualizing
- relationships, class diagrams
- types [Visual Studio], class diagrams
- relationships, visualizing
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bd28f26fe9b5a91e2b7c2a7fc95c30151f9de0c0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="viewing-types-and-relationships-class-designer"></a>查看类型和关系（类设计器）

类设计器使用类图显示类型详细信息，例如，它们的构成成员和共享的关系。 这些实体的可视化实际上是代码中的动态视图。 这意味着可以在设计器上编辑类型，然后查看反射在实体源代码中的编辑内容。 同样，类图将与对代码中的实体所做的更改保持同步。

> [!NOTE]
> 如果项目包含类图，并且项目引用了另一个项目中的类型，则在为该类型生成项目前，类图不会显示该引用的类型。 同样，在为该实体重新生成项目前，该类图不会显示对外部实体代码所做的更改。

## <a name="see-also"></a>请参阅

[设计类和类型](designing-classes-and-types.md)  
[重构类和类型](refactoring-classes-and-types.md)  
[如何：自定义类图](how-to-customize-class-diagrams.md)  
[使用类图](working-with-class-diagrams.md)