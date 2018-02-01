---
title: "查看类型和关系（类设计器）| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e9ca80f3a3feb9655d53c6ee292f84c7c567d166
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2018
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