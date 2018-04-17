---
title: 调试工作流从远程计算机 （旧版） |Microsoft 文档
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, debugging remotely
- debugging workflows, remotely
- remote debugging, workflows
- debugging, remote
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e6a3058d61d2aff0369fd52e1f03726a91a2267c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="debugging-workflows-from-a-remote-computer-legacy"></a>通过远程计算机调试工作流（旧版）
本主题介绍如何调试远程旧[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]都用旧的 Windows 工作流设计器生成的应用程序。 在应用程序需要面向 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 或 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 时，请使用旧 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]。

 当你安装[!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)]，组件安装选项之一是安装[!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)]Debugger for [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]。 这将安装远程调试组件。 必须在将要进行远程工作流调试的目标计算机上安装这些远程调试组件。

 另外，必须在用于调试的本地计算机的全局程序集缓存 (GAC) 中安装程序集，该程序集包含将在远程计算机上进行调试的旧工作流的工作流定义。 例如，如果旧工作流在远程计算机 A 上运行，而您正在从本地计算机 B 对其进行调试，则计算机 B 的 GAC 中必须存在工作流定义。这样，设计器可以将正在计算机 A 上远程运行的工作流的工作标记反序列化并将其显示在计算机 B 上。有关全局程序集缓存的更多信息，请参见 MSDN Library。

 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] 远程调试的作用方式与其他 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 组件的远程调试相同。 有关详细信息，请参阅[!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)]MSDN 库中的远程调试。

## <a name="see-also"></a>请参阅

- [调试旧版工作流](../workflow-designer/debugging-legacy-workflows.md)