---
title: 使用工具窗口创建扩展 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f918a5b8b48a7b9553cf3ca2e6c8fe9d38fbc9b8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102143"
---
# <a name="creating-an-extension-with-a-tool-window"></a>使用工具窗口创建扩展
在此过程中，你将学习如何使用 VSIX 项目模板和**自定义工具窗口**项模板，从而创建一个与工具窗口的扩展。  
  
## <a name="prerequisites"></a>系统必备  
 从 Visual Studio 2015 开始，你并不安装 Visual Studio SDK 从下载中心。 它将包括作为 Visual Studio 安装程序中的可选功能。 你还可以在以后安装 VS SDK。 有关详细信息，请参阅[安装 Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md)。  
  
### <a name="creating-a-tool-window"></a>创建工具窗口  
  
1.  创建一个名为的 VSIX 项目**FirstWindow**。 你可以查找中的 VSIX 项目模板**新项目**下的对话框**Visual C# / 可扩展性**。  
  
2.  在项目打开，添加名为的工具窗口项模板**MyWindow**。 在**解决方案资源管理器**，右键单击项目节点并选择**添加 / 新项**。 在**添加新项**对话框中，转到**Visual C# / 可扩展性**和选择**自定义工具窗口**。 在**名称**在窗口底部字段中，工具窗口文件名称更改为**MyWindow.cs**。  
  
3.  生成项目并启动调试。  
  
     将显示 Visual Studio 的实验实例。 实验实例有关的详细信息，请参阅[实验实例](../extensibility/the-experimental-instance.md)。  
  
4.  在实验实例中，转到**视图 / 其他窗口**。  
  
     你应看到的菜单项**MyWindow**。 单击此链接。  
  
     你应看到工具窗口标题**MyWindow**和按钮说**Click Me ！。**