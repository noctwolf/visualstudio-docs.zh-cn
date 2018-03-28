---
title: 扩展对象模型的基本项目 |Microsoft 文档
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a0fdda35744aaddf8789818afd1f938897470147
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="extending-the-object-model-of-the-base-project"></a>扩展基本项目对象的模型

项目子类型可能扩展自动化对象模型中的以下位置中的基本项目：

-   Project.Extender ("\<ProjectSubtypeName >")-这样项目子类型使用自定义方法从提供对象<xref:EnvDTE.Project>。 项目子类型可以使用自动化扩展程序来公开`Project`对象。 <xref:EnvDTE80.IInternalExtenderProvider>的主项目子类型聚合器上实现接口应提供有关其对象`VSHPROPID_ExtObjectCATID`从<xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2>(对应于`itemid`值[VSITEMID。根](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)) CATID。

-   ProjectItem.Extender ("\<ProjectSubtypeName >")-这样一个项目子类型，以便使用自定义方法的对象提供从特定<xref:EnvDTE.ProjectItem>项目中的对象。 项目子类型可以使用自动化扩展程序公开此对象。 <xref:EnvDTE80.IInternalExtenderProvider>的主项目子类型聚合器上实现接口需要提供其对象`VSHPROPID_ExtObjectCATID`从<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>(对应于所需<xref:Microsoft.VisualStudio.VSConstants.VSITEMID>) CATID。

-   Project.Properties-此集合公开的独立于配置的属性`Project`对象。 项目属性的详细信息，请参阅<xref:EnvDTE.Project.Properties%2A>。 项目子类型可以使用自动化扩展程序将其属性添加到此集合。 <xref:EnvDTE80.IInternalExtenderProvider>的主项目子类型聚合器上实现接口需要提供其对象`VSHPROPID_BrowseObjectCATID`从 VSHPROPID2 (对应于`itemid`值[VSITEMID。根](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)，从<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>) CATID。

-   Configuration.Properties-此集合公开为 （例如，调试） 特定的配置项目的依赖于配置的属性。 有关详细信息，请参阅<xref:EnvDTE.Configuration>。 项目子类型可以使用自动化扩展程序将其属性添加到此集合。 <xref:EnvDTE80.IInternalExtenderProvider>的主项目子类型聚合器上实现的接口提供其对象的 CATID `VSHPROPID_CfgBrowseObjectCATID` (对应于`itemid`值[VSITEMID。根](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>))。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>接口用于将一个配置浏览对象与另一个区分开来。

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>