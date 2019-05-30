---
title: 使用字体和颜色 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- fonts, controlling in IDE
- IDE, controlling text color and fonts
- Fonts and Colors property page
- font and color control [Visual Studio SDK]
- text, IDE
ms.assetid: d1a9b99f-fbdc-45ed-920a-e08c3d931ac9
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 32bbfb4957dbeb351055ab3f73c7a29087349636
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66338044"
---
# <a name="using-fonts-and-colors"></a>使用字体和颜色
[!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)]支持使用字体和颜色显示文本。

## <a name="in-this-section"></a>本节内容
- [字体和颜色概述](../extensibility/font-and-color-overview.md)讨论了中的文本字体和颜色设置[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]集成的开发环境 (IDE)。 此外引入了类别和显示项的概念，并介绍 Vspackage 和核心编辑器使用的文本特性。

- [获取字体和颜色信息对文本着色](../extensibility/getting-font-and-color-information-for-text-colorization.md)提供用于在管理的 Vspackage 中实现文本着色的指导原则**类别**以外**文本编辑器**。

- [访问存储的字体和颜色设置](../extensibility/accessing-stored-font-and-color-settings.md)解释了如何可以存储当前的字体和颜色设置、 检索和应用。

- [实现自定义类别和显示项](../extensibility/implementing-custom-categories-and-display-items.md)介绍的基本步骤，通过该窗口可以创建和使用其自己的**显示项**并**类别**为支持文本显示。

 这种方法需要实现的 VSPackage<xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>接口及相关的接口。

- [如何：访问内置的字体和配色方案](../extensibility/how-to-access-the-built-in-fonts-and-color-scheme.md)讨论如何定义和使用内置的字体和颜色，注册某个类别并启动系统提供的字体和颜色的使用。

## <a name="reference"></a>参考
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> 提供的实例`IVsFontAndColorDefaults`或<xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup>对应于特定项中列出的接口**显示设置为**列表中**字体和颜色**页**选项**对话框。

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> 启用以支持在 IDE 的 VSPackage**字体和颜色**页中按定义的窗口或 UI 组件，默认字体和颜色。

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup> 提供一种机制所依据的 VSPackage 提供字体和颜色支持可以指定显示项组-超级类别表示两个或多个类别的集合。

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> 允许 VSPackage 来检索字体和颜色数据，或将其保存到注册表。

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> 通知使用字体和颜色设置中的更改的字体和颜色信息的 Vspackage。

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorUtilities> 提供用于处理所使用的方法的输入和输出数据工具[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]**字体和颜色**机制。

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> 控制缓存的字体和颜色设置。

## <a name="related-sections"></a>相关章节
- [开发旧版语言服务](../extensibility/internals/developing-a-legacy-language-service.md)讨论 Vspackage 如何使用语言服务以自定义[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]编辑器。

- [自定义编辑器中的语法着色](../extensibility/syntax-coloring-in-custom-editors.md)Descries 如何[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]编辑器使用语言服务实现语法着色。

- [扩展其他部件的 Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)介绍了如何使用[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]服务，以创建匹配的其余部分的 UI 元素[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。