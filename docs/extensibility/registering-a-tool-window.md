---
title: 注册工具窗口 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tool windows, registering managed
- tool windows, registering
ms.assetid: 8c8c4a24-3da4-497b-9db2-0ddd7cfbfdd2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 637f0635a4f1e04df7495ab00b4e79b59d97ee1b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31136460"
---
# <a name="registering-a-tool-window"></a>注册工具窗口
你可以注册你使用的工具窗口<xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute>和  <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute>  
  
## <a name="example"></a>示例  
  
```csharp  
  
[ProvideToolWindow(typeof(PersistedWindowPane), Style = MsVsShell.VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")]
[ProvideToolWindow(typeof(DynamicWindowPane), PositionX=250, PositionY=250, Width=160, Height=180, Transient=true)]
[ProvideToolWindowVisibility(typeof(DynamicWindowPane), /*UICONTEXT_SolutionExists*/"f1536ef8-92ec-443c-9ed7-fdadf150da82")]  
[ProvideMenuResource(1000, 1)]  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")]  
public class PackageToolWindow : Package  
{  
```  
  
 在上面的代码，<xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute>注册 Visual Studio persistedwindowpane 注册和 DynamicWindowPane 工具窗口。 为持久化的工具窗口停靠，并与选项卡式**解决方案资源管理器**，并动态窗口向其授予默认起始位置和大小。 动态窗口进行暂时的指示在启动时未创建。 这将 DontForceCreate 值写入系统注册表中的 ToolWindows 项。 有关详细信息，请参阅[工具窗口显示配置](../extensibility/tool-window-display-configuration.md)。
