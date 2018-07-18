---
title: 如何：在元素上设置 CLR 特性
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: ceca2556e269d554d40e025e5edcb91753149622
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31948907"
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>如何：在元素上设置 CLR 特性
自定义特性是可以添加到域元素、 形状、 连接器和关系图的特殊属性。 你可以添加任何特性的继承自`System.Attribute`类。

### <a name="to-add-a-custom-attribute"></a>若要添加的自定义特性

1.  在**DSL 资源管理器**，选择你想要添加的自定义特性的元素。

2.  在**属性**窗口中，到下的一步**自定义特性**属性，单击浏览 (**...**) 图标。

     **编辑属性**对话框随即打开。

3.  在**名称**列中，单击**\<添加属性 >** 并键入特性的名称。 按 Enter。

4.  在属性名称的行显示括号。 在此行上键入该属性的参数类型 (例如， `string`)，然后按 ENTER。

5.  在**Name 属性**列中，键入适当的名称，例如`MyString`。

6.  单击 **“确定”**。

     **自定义特性**属性现在显示的属性采用以下格式：

     `[` *AttributeName* `(` *ParameterName* `=` *类型* `)]`

## <a name="see-also"></a>请参阅

- [域特定语言工具词汇表](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)