---
title: 向层关系图添加自定义属性 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- layer diagrams, adding custom properties
ms.assetid: 52b3ac25-d10b-4507-a1fe-209ccb4d2777
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 511f19e48f91c6719c8b0021ff7eae4071ce89b6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58934468"
---
# <a name="add-custom-properties-to-layer-diagrams"></a>向层关系图添加自定义属性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

为层关系图编写扩展代码时，可以存储具有层关系图上任何元素的值。 保存并重新打开关系图时，值将保留。 此外可以让这些属性显示在**属性**窗口，以便用户可以查看和编辑它们。 例如，您可以让用户为每一层指定正则表达式，并编写验证代码来确认每层中的类名称符合用户指定的模式。  
  
## <a name="properties-not-visible-to-the-user"></a>不向用户显示的属性  
 如果仅希望你的代码将值附加到层关系图中的任何元素，则无需定义 MEF 组件。 在 `Properties` 中有一个名为 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> 的字典。 只需将可封送的值添加到任何层元素的字典。 这些值将保存为层关系图的一部分。 有关详细信息，请参阅[导航和更新层模型在程序代码中的](../modeling/navigate-and-update-layer-models-in-program-code.md)。  
  
## <a name="properties-that-the-user-can-edit"></a>用户可以编辑的属性  
 **初始准备**  
  
> [!IMPORTANT]
>  要显示属性，您必须对要显示层属性的每台计算机做出以下更改。  
> 
> 1. 使用运行记事本**以管理员身份运行**。 打开 `%ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\extension.vsixmanifest`  
>    2.  在 `Content` 元素中，添加：  
> 
>    ```xml  
>    <MefComponent>Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.Provider.dll</MefComponent>  
>    ```  
>    3.  下**Visual Studio Tools**部分中的 Visual Studio 应用程序开始菜单，打开**开发人员命令提示**。  
> 
>    输入：  
> 
>    `devenv /rootSuffix /updateConfiguration`  
> 
>    `devenv /rootSuffix Exp /updateConfiguration`  
>    4.  重新启动 Visual Studio。  
  
 **请确保你的代码在 VSIX 项目**  
  
 如果您的属性是命令、笔势或验证项目的一部分，则无需添加任何内容。 自定义属性的代码应在 Visual Studio 扩展性项目中定义，并定义为 MEF 组件。 有关详细信息，请参阅[向层关系图添加命令和笔势](../modeling/add-commands-and-gestures-to-layer-diagrams.md)或[向层关系图添加自定义体系结构验证](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)。  
  
 **定义自定义属性**  
  
 若要创建自定义属性，请定义如下类：  
  
```  
[Export(typeof(IPropertyExtension))]  
public class MyProperty   
      : PropertyExtension<ILayerElement>  
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
  
```  
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
 [扩展层关系图](../modeling/extend-layer-diagrams.md)
