---
title: BoundsRules 约束形状位置和大小
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, events
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 8c6ab2a25838935ff0c0b7dcc860fa9196504974
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986213"
---
# <a name="boundsrules-constrain-shape-location-and-size"></a>BoundsRules 约束形状位置和大小

一个*边界规则*是一个类，用于定义限制的大小和形状的位置。 它提供时用户正在拖动形状或角部或两侧形状会反复调用的方法。

下面的示例将限制为固定大小，水平或垂直的栏的矩形形状。 当用户拖动角部或两侧时，大纲翻转之间的两个允许的配置的高度和宽度。

边界规则类派生自<xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>。 在形状中创建的规则的一个实例：

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

请注意，是否您希望，可以限制的位置和大小。

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>
- [响应并传播更改](../modeling/responding-to-and-propagating-changes.md)