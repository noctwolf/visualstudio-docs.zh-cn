---
title: 自定义 T4 文本转换
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
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7755444781bb0205e7483e2365d80cac909c62c6
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2018
ms.locfileid: "39380098"
---
# <a name="customize-t4-text-transformation"></a>自定义 T4 文本转换

文本模板是 Visual Studio，可用于生成程序代码或其他文本文件通过转换过程的一项功能。 使用[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]，可以通过自定义文本模板指令处理器或文本模板宿主扩展默认模板转换过程。

## <a name="in-this-section"></a>本节内容

 [文本模板转换过程](../modeling/the-text-template-transformation-process.md)说明文本转换的工作原理，并解释了模板宿主和指令处理器的角色。

 [创建自定义 T4 文本模板指令处理器](../modeling/creating-custom-t4-text-template-directive-processors.md)指令处理器处理指令在你的模板，如`<#@template#>.`它运行的模板，在编译过程，并可以加载程序集和其他资源。 它还可以插入代码将加载在运行时的资源。 通过定义指令处理器，可以减少您的模板的复杂性。

 [在 VS 扩展中调用文本转换](../modeling/invoking-text-transformation-in-a-vs-extension.md)如果你正在编写 Visual Studio 扩展，如菜单命令或事件处理程序，您的扩展插件可以使用文本模板化服务来转换任何文本模板。 可以将参数数据传递到模板，通过使用 Session 对象，并通过获取从模板中的值`<#@parameter#>`指令。

 [使用自定义宿主处理文本模板](../modeling/processing-text-templates-by-using-a-custom-host.md)主机时文本模板的代码执行，提供对外部文件和应用程序状态的访问。 例如，在 Visual Studio 中运行文本转换的主机可以提供访问权限**解决方案资源管理器**。 它还在错误消息窗口中显示错误。 如果你想要在不同的上下文中运行文本转换，则可以定义您自己提供对在该上下文中可用的服务的访问的主机。

 如果你正在编写一个 Visual Studio 扩展，请考虑使用现有的文本转换服务而不编写您自己的主机。 有关详细信息，请参阅[VS 扩展中调用文本转换](../modeling/invoking-text-transformation-in-a-vs-extension.md)。

## <a name="reference"></a>参考

- [编写 T4 文本模板](../modeling/writing-a-t4-text-template.md)提供文本模板指令和控制块的语法。