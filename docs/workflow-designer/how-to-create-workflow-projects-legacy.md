---
title: 如何： 创建工作流项目 （旧版） |Microsoft 文档
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflow projects, creating
- projects, workflow
ms.assetid: 32299555-662c-469d-a90d-89f4700dc78c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca6fdbbd8a744c472c06fdefbdafce77679ec2c9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-workflow-projects-legacy"></a>如何：创建工作流项目（旧版）
按照这些步骤可创建面向 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 或 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 的 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)] 项目。 此过程使用旧的 Windows 工作流设计器提供的[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]。

### <a name="to-create-a-workflow-project"></a>创建一个工作流项目

1.  启动 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)]。

2.  在“文件”菜单上，指向“新建”，然后选择“项目”。

     **“新建项目”** 对话框随即打开。

3.  选择**.NET Framework 3.0**选项或**.NET Framework 3.5**的下拉列表的顶部列表中的选项**新项目**窗口，以访问旧设计器。

    > [!NOTE]
    > 中的默认选项[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]是**.NET Framework 4**。 此选项用于创建面向 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 的 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 应用程序，并且不使用旧设计器。

4.  在**项目类型**窗格中，选择 Visual C# 项目或 Visual Basic 项目，然后选择**工作流**。

5.  在**模板**窗格中，选择已安装的项目模板之一：

    -   顺序工作流控制台应用程序

    -   顺序工作流库

    -   工作流 Activity 库

    -   状态机工作流控制台应用程序

    -   状态机工作流库

    -   空工作流项目

6.  在**名称**框中，输入你的项目，以便可以方便地标识的描述性名称。

7.  在**位置**框中，输入你要在其中保存你的项目，或单击的目录**浏览**以导航到的目录。

     如果要为项目创建解决方案目录，请选择**创建解决方案的目录**复选框，输入中的名称**解决方案名称**框。

8.  单击 **“确定”**。

## <a name="see-also"></a>请参阅

- [创建旧版工作流项目](../workflow-designer/creating-legacy-workflow-projects.md)