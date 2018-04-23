---
title: 创建源控件 VSPackage |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], creating source control packages
- source control packages
ms.assetid: cca0a9ed-48ff-409f-8036-ed8db0f7533e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8eb34efef22510d1d8f83590a6bdb7960d70ce49
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-source-control-vspackage"></a>创建源控件 VSPackage
本文档包括指向与集成源代码管理包的体系结构概述[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]，按实现的接口和要使用的服务定义的 API 和的示例演示一个简单的源控制包实现。  
  
 与源代码管理 VSPackage，你可以创建源控件与集成的深度集成路径[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。 它使包能够绕过默认的源代码管理 UI 由承载[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]，从项目系统中，响应源控制请求和与之交互[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]组件，例如**解决方案资源管理器**。 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]使[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]合作伙伴提供一种机制来创建 VSPackage 可以与集成[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]使用服务模型。  
  
## <a name="in-this-section"></a>本节内容  
 [入门](../../extensibility/internals/getting-started-with-source-control-vspackages.md)  
 讨论源代码管理包，这是源代码管理插件用于实现中的源代码管理功能的更高级的替代[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。  
  
 [体系结构](../../extensibility/internals/source-control-vspackage-architecture.md)  
 显示关系图，并说明源代码管理包的组件。  
  
 [功能](../../extensibility/internals/source-control-vspackage-features.md)  
 描述的各种功能的源代码管理包。  
  
 [设计元素](../../extensibility/internals/source-control-vspackage-design-elements.md)  
 描述源代码管理包必须为深度集成实现的 VSPackage 的结构。  
  
## <a name="related-sections"></a>相关章节  
 [创建源代码管理插件](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 讨论如何创建了源代码管理插件，提供在源代码管理功能[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]源控制用户界面 (UI)。  
  
 [源代码管理](../../extensibility/internals/source-control.md)  
 讨论用于实现的一个集成功能作为源代码管理选项[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。