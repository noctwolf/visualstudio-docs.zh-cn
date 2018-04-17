---
title: 自定义 T4 文本转换 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, API
- text templates, custom hosts
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 158e39dfe01dd0016d622918082d6ec4874dc661
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="customizing-t4-text-transformation"></a>自定义 T4 文本转换
文本模板是一项功能的[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]，可让你生成程序代码或其他通过转换过程的文本文件。 使用[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]，你可以通过自定义文本模板指令处理器或文本模板宿主扩展默认模板转换过程。  
  
## <a name="in-this-section"></a>本节内容  
 [文本模板转换过程](../modeling/the-text-template-transformation-process.md)  
 说明文本转换的工作原理，并解释模板宿主和指令处理器的角色。  
  
 [创建自定义 T4 文本模板指令处理器](../modeling/creating-custom-t4-text-template-directive-processors.md)  
 指令处理器处理指令在模板中，如`<#@template#>.`它的模板，在编译过程中运行，并且可以加载程序集和其他资源。 它还可以将插入将加载在运行时的资源的代码。 通过定义您自己的指令处理器，可以减少你的模板的复杂性。  
  
 [在 VS 扩展中调用文本转换](../modeling/invoking-text-transformation-in-a-vs-extension.md)  
 如果你正在编写[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]扩展如菜单命令或事件处理程序，你的扩展可以使用文本模板化服务转换任何文本模板。 你可以将参数数据传递到模板，通过使用会话对象，并通过使用获取模板中的值`<#@parameter#>`指令。  
  
 [使用自定义宿主处理文本模板](../modeling/processing-text-templates-by-using-a-custom-host.md)  
 文本模板的代码执行时，宿主会提供对外部文件和应用程序的状态的访问。 例如，在运行文本转换的主机[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]可提供对解决方案资源管理器访问。 它还显示在错误消息窗口中的错误。 如果你想要在不同的上下文中运行文本转换，则可以定义您自己提供对在该上下文中可用的服务的访问的主机。  
  
 如果你正在编写[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]扩展，请考虑使用现有的文本转换服务而不编写您自己的主机。 有关详细信息，请参阅[在 VS 扩展中调用文本转换](../modeling/invoking-text-transformation-in-a-vs-extension.md)。  
  
## <a name="reference"></a>参考  
 [编写 T4 文本模板](../modeling/writing-a-t4-text-template.md)  
  
 提供文本模板指令和控制块的语法。