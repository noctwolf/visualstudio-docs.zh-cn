---
title: 核心编辑器内 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - core editor
ms.assetid: 8265f31c-c45b-4858-882c-6d9f1e3b9083
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a188116b09b846e81023c239d64d6386c7f2c6ae
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60086515"
---
# <a name="inside-the-core-editor"></a>在核心编辑器
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]核心编辑器是一组让你修改和查询文本信息的多个组件。 如果已使用传统的 API 自定义核心编辑器，可以继续使用这些自定义，这将通过编辑器适配器路由。 建议，但是，调整到新的编辑器 API 自定义设置。

 以下几个方面是核心编辑器的一些重要方面：

- 文本缓冲区

- 文本视图

- “代码”窗口

- 文本标记

- 文本管理器

- 与语言服务的集成

## <a name="in-this-section"></a>本节内容
- [通过使用传统的 API 实例核心编辑器](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)提供了有关如何使用的分步说明<xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>创建编辑器的核心的一个实例。

- [通过使用传统的 API 访问的文本缓冲区](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)介绍核心编辑器中的文本缓冲区的角色，介绍了用于访问缓冲区，并提供了一系列文本缓冲区对象，实现的接口的关联的系统<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.

- [传统的 API 中的文本缓冲区事件](../extensibility/text-buffer-events-in-the-legacy-api.md)提供了一系列使用的文本缓冲区事件通知的接口。

- [如何：注册以进行传统的 API 与文本缓冲区事件](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)介绍如何向建议文本缓冲区的事件。

- [使用文本管理器来监视全局设置](../extensibility/using-the-text-manager-to-monitor-global-settings.md)讨论了如何使用文本管理器与核心编辑器组件共享全局首选项信息以及如何接收通知的文本管理器事件。

- [通过使用传统的 API 访问文本视图](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)描述核心编辑器中的文本视图的角色，并列出实现的接口<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>对象。

- [使用传统的 API 自定义代码窗口](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)提供代码窗口用于括住文本视图、 讨论如何使用代码窗口管理器来提供到代码窗口中，修饰和提供的新视图通知有关的信息.

- [通过使用传统的 API 更改视图设置](../extensibility/changing-view-settings-by-using-the-legacy-api.md)提供有关如何强制执行视图设置以及如何删除强制的设置的分步说明。

- [语言服务和核心编辑器](../extensibility/language-services-and-the-core-editor.md)描述的控件代码修饰语言服务的实例化。

## <a name="related-sections"></a>相关章节
- [演练：创建编辑器的一个核心和注册编辑器文件类型](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)提供有关如何从托管代码启动核心编辑器的分步说明。

- [下拉栏](../extensibility/drop-down-bar.md)讨论如何在代码窗口中使用下拉栏并介绍了实现下拉栏时所使用的接口。

- [与传统的 API 使用文本标记](../extensibility/using-text-markers-with-the-legacy-api.md)说明文本标记和如何在核心编辑器中使用的概念，并列出了用于访问和管理文本标记的接口。

- [如何：添加标准文本标记](../extensibility/how-to-add-standard-text-markers.md)提供了有关如何创建文本标记以及如何将自定义命令添加到快捷菜单的分步说明。

- [如何：创建自定义文本标记](../extensibility/how-to-create-custom-text-markers.md)提供了有关如何创建自定义文本标记以及如何提供的标记类型为服务的分步说明。