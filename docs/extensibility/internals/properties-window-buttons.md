---
title: 属性窗口按钮 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Properties window, buttons
ms.assetid: bdd2e3a7-ae6e-4e88-be1a-e0e3b7ddbbcc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 361333fdfceda28ecd78dc54145fded716ee81eb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130698"
---
# <a name="properties-window-buttons"></a>属性窗口按钮
根据开发语言和产品类型，某些按钮的工具栏上的默认情况下显示**属性**窗口。 在所有情况下，**按分类顺序**， **Alphabetized**，**属性**，和**属性页**按钮显示。 在 Visual C# 和 Visual Basic 中，**事件**按钮还会显示。 在某些 Visual c + + 项目中， **VC + + 消息**和**VC 替代**按钮显示。 对于其他项目类型，可能显示其他按钮。 有关详细信息中的按钮有关**属性**窗口中，请参阅[属性窗口](../../ide/reference/properties-window.md)。  
  
## <a name="implementation-of-properties-window-buttons"></a>实现的属性窗口按钮  
 当你单击**按分类顺序**按钮，Visual Studio 调用<xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties>具有焦点，若要按类别进行排序其属性的对象上的接口。 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties> 在上实现`IDispatch`对象呈现给**属性**窗口。  
  
 有 11 的预定义的属性类别，具有负值。 你可以定义自定义类别，但我们建议你将为它们分配正值，以区别于预定义的类别。  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.MapPropertyToCategory%2A>方法返回相应的属性类别值的指定属性。 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.GetCategoryName%2A>方法返回包含类别名称的字符串。 只需为自定义的类别值提供支持，因为 Visual Studio 知道标准的属性类别值。  
  
 当你单击**Alphabetized**按钮，按名称按字母顺序进行显示属性。 检索名称`IDispatch`根据本地化的排序算法。  
  
 当**属性**窗口处于打开状态，**属性**按钮自动显示为选中状态。 在环境的其他部分，将显示相同按钮，然后你可以单击它以显示**属性**窗口。  
  
 **属性页**按钮也不可用如果`ISpecifyPropertyPages`不会为所选对象实现。 属性页通常与解决方案和项目中，关联的显示依赖于配置的属性，但它们还可以与项目项 （例如，在 Visual c + +） 相关联。  
  
> [!NOTE]
>  无法添加到工具栏按钮**属性**使用非托管的代码的窗口。 若要添加工具栏按钮，你必须创建派生自的托管的对象<xref:System.Windows.Forms.Design.PropertyTab>。  
  
## <a name="see-also"></a>另请参阅  
 [扩展属性](../../extensibility/internals/extending-properties.md)