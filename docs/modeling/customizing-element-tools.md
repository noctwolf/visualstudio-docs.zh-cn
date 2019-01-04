---
title: 自定义元素工具
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: ee9f574b1d0db7a90b2d056456ccb29db0604e1e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53846095"
---
# <a name="customizing-element-tools"></a>自定义元素工具
在一些 DSL 定义中，在一个概念表示为一组元素。 例如，如果您创建模型，在其中一个组件具有一组固定的端口，您始终想要在其父组件在同一时间创建的端口。 因此，您必须自定义元素创建工具，使其创建的一组而不是只是一个元素。 若要实现此目的，你可以自定义如何初始化的元素创建工具。

 您还可以重写该工具拖动到关系图或元素上时，会发生什么情况。

## <a name="customizing-the-content-of-an-element-tool"></a>自定义元素工具的内容
 每个元素工具将存储的实例<xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype>(EGP)，其中包含的一个或多个模型元素和链接序列化的版本。 默认情况下，元素工具 EGP 包含为工具指定类的一个实例。 您可以通过重写来更改此*YourLanguage*`ToolboxHelper.CreateElementToolPrototype`。 DSL 包加载时，调用此方法。

 方法的一个参数是类的在 DSL 定义中指定的 ID。 与您感兴趣的类调用方法时，您可以将额外的元素添加到 EGP。

 EGP 必须包括嵌入附属元素从一个主要元素的链接。 它还可以包含引用链接。

 以下示例创建一个主要元素和两个嵌入的元素。 主类称为电阻器，，它具有两个名为终端的元素的嵌入关系。 嵌入的角色属性名为 Terminal1 和 Terminal2，并且两者都重数 1..1。

```csharp
using Microsoft.VisualStudio.Modeling; ...
public partial class CircuitDiagramToolboxHelper
{
  protected override ElementGroupPrototype    CreateElementToolPrototype(Store store, Guid domainClassId)
  {
    // A case for each tool to customize:
    if (domainClassId == Resistor.DomainClassId)
    {
      // Set up the prototype elements and links:
      Resistor resistor = new Resistor(store);
      resistor.Terminal1 = new Terminal(store);
      resistor.Terminal2 = new Terminal(store);
      resistor.Terminal1.Name = "T1"; // embedding
      resistor.Terminal2.Name = "T2"; // embedding
      // We could also set up reference links.

      // Create an element group prototype for the toolbox:
      ElementGroup egp = new ElementGroup(store.DefaultPartition);
      egp.AddGraph(resistor, true);
      // We do not have to explicitly include embedded children.
      return egp.CreatePrototype();
    }
    // Element tools for other classes:
    else
      return base.CreateElementToolPrototype(store, domainClassId);
  }
}
```

## <a name="see-also"></a>请参阅

- [自定义元素创建和移动](../modeling/customizing-element-creation-and-movement.md)