---
title: 创作 Windows Installer 程序包 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- .msi files, VSPackages
- msi files, VSPackages
ms.assetid: 0ce7c21d-0d3f-47fe-a0bb-eed506e32609
caps.latest.revision: 21
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 22dcd12eb366504ee1e7cdd19970ffe9913241bd
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49862913"
---
# <a name="authoring-a-windows-installer-package"></a>创作 Windows Installer 程序包
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

数据驱动器的 Windows 安装程序模型。 而不是编写过程的脚本，以将文件复制和写入注册表项，例如，您创建行和列中包含的文件和注册表数据的数据库表。  
  
## <a name="database-entries"></a>数据库项  
 若要安装 VSPackage，Windows Installer 包必须包含数据库条目，执行以下任务：  
  
- 搜索系统以找到的版本[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]你的 VSPackage 支持 （使用包括 AppSearch、 CompLocator、 RegLocator、 DrLocator 和签名的 Windows Installer 表）。  
  
- 如果没有受支持的版本取消安装[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]安装或如果不满足的 VSPackage 的另一个系统要求 （使用 LaunchCondition 表）。  
  
- 安装 VSPackage 和相关文件 （使用目录、 组件和文件表）。  
  
- 将 vspackage 的相应信息添加到注册表 （使用注册表表）。  
  
- 将集成在 VSPackage[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]通过调用**devenv.exe /setup** （使用 CustomAction 表）。  
  
  有关详细信息，请参阅[Windows 安装程序](http://msdn.microsoft.com/library/cc185688\(VS.85\).aspx)。  
  
## <a name="setup-tools"></a>安装程序工具  
 各种第三方安装程序工具提供了 Windows Installer 程序包的开发环境。 两个免费工具如下所示：  
  
- InstallShield Limited Edition  
  
   您可以通过 Visual Studio 获得有限的版本的 InstallShield**新的项目**对话框。 展开**其他项目类型**，然后选择**安装和部署**。 选择 InstallShield 模板。  
  
- Windows Installer XML 工具集  
  
   该工具集生成 XML 源文件从 Windows Installer 程序包。 该工具集是 Microsoft 的开源项目。 您可以下载源代码和从可执行文件[ http://sourceforge.net/projects/wix ](http://sourceforge.net/projects/wix)。  
  
  为将集成到商业产品[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]通过使用[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)]，请参阅[ http://visualstudiogallery.com ](http://visualstudiogallery.com/)。  
  
## <a name="see-also"></a>请参阅  
 [使用 Windows Installer 安装 VSPackage](../../extensibility/internals/installing-vspackages-with-windows-installer.md)

