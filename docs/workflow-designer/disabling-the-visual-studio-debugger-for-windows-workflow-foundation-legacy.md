---
title: 工作流设计器-禁用 Visual Studio Debugger for Windows Workflow Foundation （旧版）
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, disabling debugger
- debugging workflows, disabling debugger
- workflow debugger, disabling
ms.assetid: 9da96d0e-f941-4fa9-a1a5-6bab50adfec9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 473ee507e35f5ec5df902df64ee34326dcf90a2b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31969960"
---
# <a name="disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>禁用 Visual Studio Debugger for Windows Workflow Foundation（旧版）

本主题介绍如何禁用 Visual Studio 调试器生成旧的 Windows 工作流设计器中的 Windows Workflow Foundation (WF) 应用程序时使用配置文件。 当你需要以面向.NET Framework 版本 3.5 或 WinFX 时，请使用旧工作流设计器。

 默认情况下，主机进程启用的 Visual Studio 调试器的 Windows Workflow Foundation (WF)。 若要禁用工作流调试，你必须显式将其关闭通过添加"DisableWorkflowDebugging"项**\<交换机 >** 中的元素 **\<system.diagnostics >** 主机配置文件节。

 以下示例显示如何修改主机配置文件以禁用工作流调试。

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <system.diagnostics>
      <switches>
         <add name="DisableWorkflowDebugging" value="true"/>
      </switches>
   </system.diagnostics>
</configuration>
```

## <a name="see-also"></a>请参阅

- [调用 Visual Studio Debugger for Windows Workflow Foundation（旧版）](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)
- [调试旧版工作流](../workflow-designer/debugging-legacy-workflows.md)