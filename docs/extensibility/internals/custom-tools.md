---
title: 自定义工具 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, custom tools
- tools [Visual Studio], custom
- custom tools
ms.assetid: d669f154-9b23-48b6-b9f6-7419c8dd61a6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dc6093d9bdbd780e1c8ddeb941f5f80dd479f77a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607598"
---
# <a name="custom-tools"></a>自定义工具
*自定义工具*可将工具与项目中的项相关联，并运行该工具，每次保存该文件。 某些自定义工具，有时称为*单个文件生成器*，通常用于实现转换器生成代码中的数据，反之亦然。 例如，单个文件生成器创建[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]并[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]源代码共 *.settings*并 *.resx*文件。 生成的源代码提供强类型化中的数据的访问权限 *.settings*并 *.resx*文件。 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]和[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]项目类型支持自定义工具;[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]项目类型不这样做。 你自己的项目类型还可以支持自定义工具。

 自定义工具是实现的已注册的组件`IVsSingleFileGenerator`接口。

 与之关联的自定义工具`ProjectItem`接口对象，并如下所示设计器和编辑器。 自定义工具将表示的文件`ProjectItem`作为输入，并将其文件名称提供的一个新文件写入`DefaultExtension`方法。

## <a name="in-this-section"></a>本节内容
- [实现单个文件生成器](../../extensibility/internals/implementing-single-file-generators.md)

 介绍如何使用<xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>接口实现一个自定义工具。

- [注册单个文件生成器](../../extensibility/internals/registering-single-file-generators.md)

 介绍了自定义工具的所有注册表项。

- [可视化设计器向公开类型](../../extensibility/internals/exposing-types-to-visual-designers.md)

 介绍了如何项目系统支持对访问生成类和类型的可视化设计器通过提供临时可移植可执行文件 (PE) 文件。

- [保存项目项的属性](../../extensibility/persisting-the-property-of-a-project-item.md)

 演示如何持久保存项目项属性，例如源代码文件，在项目文件中的作者。

## <a name="reference"></a>参考
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> 详细介绍<xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>，其中将一个输入的文件转换为可以编译或添加到项目中的单个输出文件。

 <xref:EnvDTE.ProjectItem> 介绍了`ProjectItem`接口，它表示项目中的项。

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A> 详细介绍`DefaultExtension`方法，检索提供给输出文件的名称的文件扩展名。

## <a name="related-sections"></a>相关章节
- [扩展项目](../../extensibility/extending-projects.md)

 介绍如何使用 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 项目和解决方案来组织代码文件和资源文件，以及如何实现源代码管理。