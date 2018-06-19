---
title: 安装 Visual Studio SDK |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: c730edb6-5099-4c16-85a8-08def09f1455
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 259646e0dbee4831db83a7098954d1c5144d8ead
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129069"
---
# <a name="installing-the-visual-studio-sdk"></a>安装 Visual Studio SDK
Visual Studio SDK 是一项可选功能在 Visual Studio 安装。 你还可以在以后安装 VS SDK。  
  
## <a name="installing-the-visual-studio-sdk-as-part-of-a-visual-studio-installation"></a>作为 Visual Studio 安装的一部分安装的 Visual Studio SDK  
 如果你想要在 Visual Studio 安装中包括 VSSDK，则应安装**Visual Studio 扩展开发**下的工作负荷**其他工具集**。 这将安装 Visual Studio SDK，以及所必需的先决条件。 您可以进一步调整安装，通过选择或取消选择组件从摘要视图。 
  
## <a name="installing-the-visual-studio-sdk-after-installing-visual-studio"></a>在安装 Visual Studio 后安装 Visual Studio SDK  
 如果你决定完成你的 Visual Studio 安装之后安装 Visual Studio SDK，重新运行 Visual Studio 安装程序并选择**Visual Studio 扩展开发**工作负荷。  
  
## <a name="installing-the-visual-studio-sdk-from-a-solution"></a>从解决方案安装 Visual Studio SDK  
 如果你具有可扩展性项目中打开的解决方案不首先安装 VSSDK，解决方案资源管理器上方突出显示的信息栏将提示你。 其外观应类似于以下内容：  
  
 ![SolutionExplorerInstall](../extensibility/media/solutionexplorerinstall.png "SolutionExplorerInstall")  
  
## <a name="installing-the-visual-studio-sdk-from-the-command-line"></a>从命令行安装 Visual Studio SDK  
与任何 Visual Studio 工作负荷或组件，你可以安装**Visual Studio 扩展开发**工作负荷 (ID: Microsoft.VisualStudio.Workload.VisualStudioExtension) 从命令行。 请参阅[使用命令行参数来安装 Visual Studio](../install/use-command-line-parameters-to-install-visual-studio.md)有关适当的命令行开关和确定工作负荷或组件标识符的一般说明的详细信息。
  
 请注意，你必须使用的 Visual Studio 安装程序已安装 Visual Studio 的版本匹配。 例如，如果必须在计算机上安装的 Visual Studio Enterprise，你必须运行 Visual Studio Enterprise 安装程序 (vs_enterprise.exe)。