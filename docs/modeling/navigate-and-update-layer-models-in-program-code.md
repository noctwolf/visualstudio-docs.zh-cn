---
title: 在程序代码中导航和更新层模型
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- layer models, navigating in program code
- layer models, updating in program code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 2be7a0fdb3204647f6874d2dceaa81eb8cac3756
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="navigate-and-update-layer-models-in-program-code"></a>在程序代码中导航和更新层模型

本文介绍的元素和层模型中，你可以导航和更新使用程序代码中的关系。 有关从用户的角度来看的依赖项关系图的详细信息，请参阅[依赖项关系图： 参考](../modeling/layer-diagrams-reference.md)和[依赖项关系图： 准则](../modeling/layer-diagrams-guidelines.md)。

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer>本主题中所述的模型是一个更宽泛的外观<xref:Microsoft.VisualStudio.GraphModel>模型。 如果你正在编写[菜单命令或笔势扩展](../modeling/add-commands-and-gestures-to-layer-diagrams.md)，使用`Layer`模型。 如果你正在编写[层验证扩展](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)，很容易地使用`GraphModel`。

## <a name="transactions"></a>事务

在更新模型时，请考虑将更改包含在`ILinkedUndoTransaction`，来将你的更改到一个事务。 如果失败的任何更改，将回滚整个事务。 如果用户撤消一个更改，那么所有更改都都在一起撤消。

```
using (ILinkedUndoTransaction t =
        LinkedUndoContext.BeginTransaction("a name"))
{
    // Make changes here ....
    t.Commit(); // Don't forget this!
}
```

## <a name="containment"></a>包含

![ILayer 和 ILayerModel 都可以包含 ILayers。](../modeling/media/layerapi_containment.png)

层 (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayer>) 和层模型 (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerModel>) 可以包含注释和层。

层 (`ILayer`) 可以包含在层模型 (`ILayerModel`) 中，也可以嵌套在另一个 `ILayer` 中。

若要创建注释或层，则对相应容器使用创建方法。

## <a name="dependency-links"></a>依赖关系链接

依赖关系链接由一个对象表示。 可以在任一方向导航链接：

![一个 ILayerDependencyLink 连接到两个 ILayers。](../modeling/media/layerapi_dependency.png)

若要创建依赖关系链接，请调用 `source.CreateDependencyLink(target)`。

## <a name="comments"></a>注释

注释可以包含在层或层模型内部，也可以链接到任何层元素：

![可以将注释附加到任何层元素。](../modeling/media/layerapi_comments.png)

注释可以链接到任意数量的元素，也可以不链接任何元素。

若要获取附加到层元素的注释，请使用：

```csharp
ILayerModel model = diagram.GetLayerModel();
IEnumerable<ILayerComment> comments =
   model.Comments.Where(comment =>
      comment.Links.Any(link => link.Target == layerElement));
```

> [!CAUTION]
> `Comments` 的 `ILayer` 属性可获取包含在 `ILayer` 内的注释。 但不会获取链接到它的注释。

通过调用创建注释`CreateComment()`对相应容器。

通过对注释使用 `CreateLink()` 来创建链接。

## <a name="layer-elements"></a>层元素

可包含在一个模型中的所有类型的元素都是层元素：

![依赖项关系图内容为 ILayerElements。](../modeling/media/layerapi_layerelements.png)

## <a name="properties"></a>属性

每个 `ILayerElement` 都有一个名为 `Properties` 的字符串字典。 可以使用此字典将任意信息附加到任何层元素。

## <a name="artifact-references"></a>项目引用

项目引用 (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerArtifactReference>) 表示层和项目项（例如文件、类或文件夹）之间的链接。 在创建一个层或向其添加通过拖动到依赖项关系图从解决方案资源管理器、 类视图或对象浏览器中拖动项时，用户创建项目。 可将任意数量的项目引用链接到一个层。

“层资源管理器”中的每一行都显示一个项目引用。 有关详细信息，请参阅[在代码中创建依赖项关系图](../modeling/create-layer-diagrams-from-your-code.md)。

下面是与项目引用有关的主要类型和方法：

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerArtifactReference>。 Categories 属性指示引用的项目类型，例如类、可执行文件或程序集。 Categories 属性确定标识符标识目标项目的方式。

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ArtifactReferenceExtensions.CreateArtifactReferenceAsync%2A> 从 <xref:EnvDTE.Project> 或 <xref:EnvDTE.ProjectItem> 创建项目引用。 这是一个异步操作。 因此，你通常要提供创建完成时调用的回调。

层项目引用到项目在中是不同用例关系图。

## <a name="shapes-and-diagrams"></a>形状和关系图

使用两个对象表示层模型中的每个元素：<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> 和 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IShape>。 `IShape` 表示关系图上形状的位置和大小。 在层模型中，每个`ILayerElement`有一个`IShape`，每个`IShape`上一个依赖项关系图有一个`ILayerElement`。 `IShape` 还用于 UML 模型。 因此，并不是每一个 `IShape` 都具有层元素。

按同样的方式，<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerModel> 显示在一个 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IDiagram> 上。

在自定义命令或笔势处理程序的代码中，你可以从 `DiagramContext` 导入中获取当前关系图和当前选择的形状：

```
public class ... {
[Import]
    public IDiagramContext DiagramContext { get; set; }
...
public void ... (...)
{ IDiagram diagram = this.DiagramContext.CurrentDiagram;
  ILayerModel model = diagram.GetLayerModel();
  if (model != null)
  { foreach (ILayer layer in model.Layers) { ... }}
  foreach (IShape selected in diagram.SelectedShapes)
  { ILayerElement element = selected.GetLayerElement();
    if (element != null) ... }}
```

![每个 ILayerElement 都由一个 IShape 表示。](../modeling/media/layerapi_shapes.png)

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IShape> 和 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IDiagram> 也用于显示 UML 模型。

## <a name="see-also"></a>请参阅

- [向依赖项关系图添加命令和手势](../modeling/add-commands-and-gestures-to-layer-diagrams.md)
- [向依赖项关系图添加自定义体系结构验证](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)
- [向依赖项关系图添加自定义属性](../modeling/add-custom-properties-to-layer-diagrams.md)
- [依赖项关系图：参考](../modeling/layer-diagrams-reference.md)
- [依赖项关系图：指南](../modeling/layer-diagrams-guidelines.md)
