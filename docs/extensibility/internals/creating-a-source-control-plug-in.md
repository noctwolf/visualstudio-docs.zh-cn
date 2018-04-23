---
title: 创建源代码管理插件 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- plug-ins, source control
- source control plug-ins
- source control [Visual Studio SDK], plug-ins
ms.assetid: c7e69fa4-150e-469a-a6fc-fa1260bdbb07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 04c6125004aaf2740b54acdce91bef032647c6e5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-source-control-plug-in"></a>创建源代码管理插件
Visual Studio SDK 提供了使你能够添加到源控件功能的资源[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]集成的开发环境 (IDE)。 它允许你使用源控件插件 API 本文档中所述使用符合的任何插件 DLL。  
  
## <a name="in-this-section"></a>本节内容  
 [入门](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)  
 描述如何安装了源代码管理插件并突出显示的当前可用的源控件插件 API 版本。  
  
 [体系结构](../../extensibility/internals/source-control-plug-in-architecture.md)  
 使用体系结构关系图说明了源代码管理插件使用的集成[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]IDE。  
  
 [源代码管理插件的测试指南](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)  
 提供有关如何测试的安装和源代码管理插件的操作指南。  
  
## <a name="related-sections"></a>相关章节  
 [创建源代码管理 VSPackage](../../extensibility/internals/creating-a-source-control-vspackage.md)  
 讨论如何创建一个源控件不仅提供源代码管理功能，但是替换的 VSPackage[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]源代码管理 UI。  
  
 [源代码管理插件](../../extensibility/source-control-plug-ins.md)  
 提供源控制插件 API 中的所有元素的完整的列表。  
  
 [源代码管理](../../extensibility/internals/source-control.md)  
 讨论用于实现的一个集成功能作为源代码管理选项[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。