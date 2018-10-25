---
title: 卸载 Visual Studio |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- uninstalling
- uninstalling visual studio
- uninstall
- uninstall Visual Studio
ms.assetid: 0e445255-b796-426d-ad93-a4d8e36da2c5
caps.latest.revision: 9
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 3ec83128682a874a5491d62762b424045f11c4b2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49849848"
---
# <a name="uninstall-visual-studio"></a>卸载 Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 2017 的最新文档，请参阅[卸载 Visual Studio 2017](https://docs.microsoft.com/visualstudio/install/uninstall-visual-studio)。

此页面将引导你通过卸载 Visual Studio 2015 中，我们提供的面向开发人员工作效率工具集成套件的早期版本。  
  
##  <a name="uninstalling"></a>   
#### <a name="to-uninstall-visual-studio-by-using-the-standard-uninstallation-method"></a>若要使用"标准"卸载方法卸载 Visual Studio  
  
1. 在中**Control Panel**，然后在**程序和功能**页上，选择你想要卸载，然后选择的产品版本**更改**。  
  
2. 在安装向导中，选择**卸载**，选择**是**，然后按照向导中的其余说明进行操作。  
  
   此标准或默认方法会使某些项首次安装的 Visual Studio 时原先安装 （例如，Microsoft.NET Framework、 Microsoft Visual c + + 可再发行组件，Microsoft SQL Server 等）。   我们保留这些安装，因为其他许多应用程序依赖于它们。 但是，如果你想要同时删除它们，选择在其条目**程序和功能**，，然后分别单独删除。  
  
#### <a name="to-uninstall-visual-studio-and-all-other-related-files-that-is-to-uninstall-almost-everything"></a>若要卸载 Visual Studio 和相关的所有其他文件 (即卸载几乎所有内容)  
  
1.  找到 Visual Studio.exe 文件 （例如，找到"vs_enterprise.exe"）。  
  
    > [!NOTE]
    >  该文件应为"%ProgramData%\Package Cache"的子文件夹中为例： C:\ProgramData\Package 缓存\\{37e19555-e88d-4aed-9d42-82d0784d2b79} \vs_enterprise.exe  
  
2.  使用运行.exe 文件 /uninstall /force 命令行参数。  
  
     例如，运行```vs_enterprise.exe /uninstall /force```，这将默认卸载中删除 Visual Studio 和大部分遗留的核心组件。 但是，它不会删除所有其他内容的 Visual Studio 外接程序和扩展可以安装 （如 Visual Studio 更新和其他可选组件）。  
  
    > [!TIP]
    > 或者，可以使用"**Total Uninstaller**"工具来删除所有内容，Visual Studio 或 Visual Studio 更新可能已安装。 也就是说，任何版本的 Visual Studio 2013 或更高版本。 若要获取详细信息，请参阅[Visual Studio 卸载程序工具](https://github.com/Microsoft/VisualStudioUninstaller/releases)GitHub 上。  
  
#### <a name="to-uninstall-visual-studio-in-silent-or-passive-modes-that-is-to-uninstall-from-source"></a>若要在无提示或被动模式下卸载 Visual Studio (即，从源中卸载)  
  
1.  在安装了 Visual Studio 的计算机上，打开 Windows 命令提示符。  
  
2.  输入以下参数：  
  
     *DVDRoot* \\< 安装文件\> \</quiet/&#124;/被动 > [/norestart] /uninstall  
  
#### <a name="to-roll-back-to-a-previous-version-or-release-of--visual-studio"></a>若要回滚到以前的版本或版本的 Visual Studio  
  
1. 通过使用任何本主题中列出的方法卸载 Visual Studio。  
  
   > [!WARNING]
   >  卸载当前版本的 Visual Studio （或 Visual Studio 更新），然后安装以前的版本可能不按预期工作。  
   >   
   >  结果取决于哪个版本或版本的 Visual Studio 已安装，安装其组件的版本，所安装的产品与 Visual Studio 版本或其组件，可能也具有依赖项和最后，在你打算安装或重新安装 Visual Studio 早期版本。  鉴于所有这些变量，标准卸载通常会保留组件可能与 Visual Studio 早期版本或版本不兼容。  
   >   
   >  因此，为了获得最佳结果，我们建议使用[Visual Studio 卸载程序工具](https://github.com/Microsoft/VisualStudioUninstaller/releases)。  
  
2. 安装或重新安装你想要使用的 Visual Studio 的早期版本。  
  
   即使安装以前版本的 Visual Studio，安装程序可能仍尝试使用较新版本或发行版，如果有可用。 有关详细信息，请参阅[如何： 安装特定版本的 Visual Studio](../install/how-to-install-a-specific-release-of-visual-studio.md)主题。  
  
## <a name="see-also"></a>请参阅  
 [安装 Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx)