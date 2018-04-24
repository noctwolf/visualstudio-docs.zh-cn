---
title: BoundsRules 约束形状位置和大小
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, events
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 69e189b8348b7c68c7a778f00975d5d1475223ab
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="boundsrules-constrain-shape-location-and-size"></a>BoundsRules 约束形状位置和大小

A*边界规则*是一个类，它定义的大小和形状的位置上的限制。 它提供的用户正在拖动形状或角或两边的形状时重复调用的方法。

下面的示例约束是条形图的固定大小，水平或垂直矩形形状。 当用户拖动的角或侧时，大纲翻转之间的两个允许的配置的高度和宽度。

边界规则类派生自<xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>。 在形状中创建的规则的实例：

```csharp
using Microsoft.VisualStudio.Modeling.Diagrams; ...

public partial class BarShape
{
  /// <summary>
  /// Rule invoked when the user is resizing a shape.
  /// </summary>
  public override BoundsRules BoundsRules
  { get { return new BarBoundsRule(); } }
}

/// <summary>
/// Rule invoked when the user is changing a shape's outline.
/// Provides real-time mouse rubber-band feedback, so must work fast.
/// </summary>
public class BarBoundsRule: BoundsRules
{
  public override RectangleD GetCompliantBounds
     (ShapeElement shape, RectangleD proposedBounds)
  {
    double thickness = 0.1;
    if (proposedBounds.Height > proposedBounds.Width)
    {
      // There is a minimum width for a shape; the width
      // will actually be set to the lesser of
      // thickness and that minimum.
      return new RectangleD(proposedBounds.Location,
            new SizeD(thickness, proposedBounds.Height));
    }
    else
    {
      // There is a minimum height for a shape; the
      // height will actually be set to the lesser of
      // thickness and that minimum.
      return new RectangleD(proposedBounds.Location,
         new SizeD(proposedBounds.Width, thickness));
} } }
```

请注意是否你想，可以约束的位置和大小。

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>
- [响应并将更改传播](../modeling/responding-to-and-propagating-changes.md)