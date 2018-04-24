---
title: 控制颜色、线型和其他形状属性
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 710e4a20d0b9cc60a32786836fda7716a70f86e5
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="controlling-color-line-style-and-other-shape-properties"></a>控制颜色、线型和其他形状属性
某些形状属性如颜色可以公开-即，链接到形状的域属性。 其他需要直接控制。

## <a name="exposing-a-property"></a>公开属性
 如颜色某些形状属性可以链接到域属性的值。

 在 DSL 定义中，选择形状、 连接器或关系图类。 其上下文菜单上，选择**添加公开**，然后选择你想，如填充颜色的属性。

 形状现在具有一个域属性，你可以在程序代码中或作为用户设置。

## <a name="dynamically-updating-an-exposed-property"></a>动态更新公开的属性
 通常，你想要公开的属性依赖于另一个属性。 例如，你可能想小于零的某个形状将特定域属性时变为红色。 若要使此依赖关系，创建[规则](../modeling/rules-propagate-changes-within-the-model.md)。 例如：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Diagrams;
namespace ExampleNamespace
{
 // Attribute associates the rule with class:
 [RuleOn(typeof(CarShape), FireTime = TimeToFire.TopLevelCommit)]
 // The rule is a class derived from one of the abstract rules:
 class CarShapeAddRule : AddRule
 {
 // Override the abstract method:
 public override void ElementAdded(ElementAddedEventArgs e)
 {
 base.ElementAdded(e);
 CarShape shape = e.ModelElement as CarShape;
 Store store = shape.Store;
 // Ignore this call if we're currently loading a model:
 if (store.TransactionManager.CurrentTransaction.IsSerializing)
  return;
 Car car = shape.ModelElement as Car;
 // Code here propagates change as required - for example:
 shape.FillColor = car.Somebool ? System.Drawing.Color.Red : System.Drawing.Color.Green;
 }
}
 // The rule must be registered:
 public partial class ExampleDomainModel
 {
 protected override Type[] GetCustomDomainModelTypes()
 {
  List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());
  types.Add(typeof(CarShapeAddRule));
  // If you add more rules, list them here.
  return types.ToArray();
 }
 }
}
```