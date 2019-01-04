---
title: 向依赖项关系图添加自定义属性
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, adding custom properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 407db46519872d8f1c4e6eba79ddd5ca84610d70
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53892233"
---
# <a name="add-custom-properties-to-dependency-diagrams"></a>向依赖项关系图添加自定义属性

编写时依赖项关系图的扩展插件代码，可以依赖项关系图上存储的任何元素的值。 保存并重新打开关系图时，值将保留。 此外可以让这些属性显示在**属性**窗口，以便用户可以查看和编辑它们。 例如，你可以让用户为每一层指定正则表达式，并编写验证代码来确认每层中的类名称符合用户指定的模式。

## <a name="non-visible-properties"></a>非可见属性

如果只是想您的代码以将值附加到依赖项关系图中的任何元素，不需要定义 MEF 组件。 在 `Properties` 中有一个名为 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> 的字典。 只需将可封送的值添加到任何层元素的字典。 它们将作为依赖项关系图的一部分保存。 有关详细信息，请参阅[导航和更新层模型在程序代码中的](../modeling/navigate-and-update-layer-models-in-program-code.md)。

## <a name="editable-properties"></a>可编辑的属性

**初始准备**

> [!IMPORTANT]
> 要显示属性，请在想要显示层属性每台计算机上进行以下更改：
>
> 1. 使用运行记事本**以管理员身份运行**。 打开 *%ProgramFiles%\Microsoft Visual Studio [version] \Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\extension.vsixmanifest*。
> 2. 内部**内容**元素中，添加：
>
>     ```xml
>     <MefComponent>Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.Provider.dll</MefComponent>
>     ```
> 3. 下**Visual Studio Tools**部分中的 Visual Studio 应用程序开始菜单，打开**开发人员命令提示**。 输入：
>
>      `devenv /rootSuffix /updateConfiguration`
>
>      `devenv /rootSuffix Exp /updateConfiguration`
> 4. 重新启动 Visual Studio。

**请确保你的代码在 VSIX 项目**

如果属性为命令、 笔势或验证项目的一部分，你不必添加任何内容。 自定义属性的代码应在 Visual Studio 扩展性项目中定义，并定义为 MEF 组件。 有关详细信息，请参阅[向依赖项关系图添加命令和笔势](../modeling/add-commands-and-gestures-to-layer-diagrams.md)或[向依赖项关系图添加自定义体系结构验证](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)。

**定义自定义属性**

若要创建自定义属性，请定义如下类：

```csharp
[Export(typeof(IPropertyExtension))]
public class MyProperty : PropertyExtension<ILayerElement>
{
  // Implement the interface.
}
```

可以在 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> 或其任何派生类上定义属性，派生类包括：

-   `ILayerModel` - 模型

-   `ILayer` - 每一层

-   `ILayerDependencyLink` - 层与层之间的链接

-   `ILayerComment`

-   `ILayerCommentLink`

## <a name="example"></a>示例

以下代码是典型的自定义属性描述符。 它在层模型 (`ILayerModel`) 上定义了一个布尔属性，用户可以使用该布尔属性来为自定义的验证方法提供值。

```csharp
using System;
using System.ComponentModel.Composition;
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;

namespace MyNamespace
{
  /// <summary>
  /// Custom properties are added to the Layer Designer via a custom
  /// Property Descriptor. We have to export this Property Descriptor
  /// using MEF to make it available in the Layer Designer.
  /// </summary>
  [Export(typeof(IPropertyExtension))]
  public class AllTypesMustBeReferencedProperty
      : PropertyExtension<ILayerModel>
  {
    /// <summary>
    /// Each custom property must have a unique name.
    /// Usually we use the full name of this class.
    /// </summary>
    public static readonly string FullName =
      typeof(AllTypesMustBeReferencedProperty).FullName;

    /// <summary>
    /// Construct the property. Notice the use of FullName.
    /// </summary>
    public AllTypesMustBeReferencedProperty()
            : base(FullName)
    {  }

    /// <summary>
    /// The display name is shown in the Properties window.
    /// We therefore use a localizable resource.
    /// </summary>
    public override string DisplayName
    {
      get { return Strings.AllTypesMustBeReferencedDisplayName; }
    }

    /// <summary>
    /// Description shown at the bottom of the Properties window.
    /// We use a resource string for easier localization.
    /// </summary>
    public override string Description
    {
      get { return Strings.AllTypesMustBeReferencedDescription; }
    }

    /// <summary>
    /// This is called to set a new value for this property. We must
    /// throw an exception if the value is invalid.
    /// </summary>
    /// <param name="component">The target ILayerElement</param>
    /// <param name="value">The new value</param>
    public override void SetValue(object component, object value)
    {
      ValidateValue(value);
      base.SetValue(component, value);
    }
    /// <summary>
    /// Helper to validate the value.
    /// </summary>
    /// <param name="value">The value to validate</param>
    private static void ValidateValue(object value)
    {  }

    public override Type PropertyType
    { get { return typeof(bool); } }

    /// <summary>
    /// The segment label of the properties window.
    /// </summary>
    public override string Category
    {
      get
      {
        return Strings.AllTypesMustBeReferencedCategory;
      }
    }
  }
}
```

## <a name="see-also"></a>请参阅

- [扩展依赖项关系图](../modeling/extend-layer-diagrams.md)
