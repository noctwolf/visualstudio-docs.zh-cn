---
title: VSPackage 开发的 Devenv 命令行开关 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- /setup command line switch
- /resetskippkgs command line switch
- /noVSIP command line switch
- /rootsuffix command line switch
- command-line switches
- registry, Visual Studio SDK
- command line, switches
- Visual Studio SDK, command-line switches
ms.assetid: d65d2c04-dd84-42b0-b956-555b11f5a645
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8adf9480f426f8f19ef9e74c3417dc170b2e24ed
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39636556"
---
# <a name="devenv-command-line-switches-for-vspackage-development"></a>VSPackage 开发的 Devenv 命令行开关
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 允许开发人员自动执行任务命令行中的，执行时*devenv.exe*，启动 Visual Studio 集成的开发环境 (IDE) 的文件。  
  
 任务包括：  
  
-   在从 IDE 外部的预配置中部署应用程序。  
  
-   自动使用预设的生成项目的生成设置，或调试配置。  
  
-   在 IDE 之外，在特定配置中，IDE 加载中的所有内容。 此外，您可以自定义在启动时 IDE。  
  
## <a name="guidelines-for-switches"></a>开关的准则  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 文档介绍了用户级 devenv 命令行开关。 有关详细信息，请参阅[Devenv 命令行开关](../ide/reference/devenv-command-line-switches.md)。 Devenv 还支持用于 VSPackage 开发、 部署和调试的其他命令行开关。  
  
|命令行开关|描述|  
|--------------------------|-----------------|  
|/safemode|启动[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]在安全模式下加载的默认 IDE 和服务。 /Safemode 开关可阻止所有第三方 VSPackages 加载时[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]启动后，以此确保执行稳定。<br /><br /> 此开关不带参数。|  
|/resetskippkgs|清除所有跳过加载选项已添加的用户想要避免加载有问题的 Vspackage，然后启动[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。 SkipLoading 标记的状态禁用 VSPackage 加载。 清除这些标记将重新启用 VSPackage 的加载。<br /><br /> 此开关不带参数。|  
|/rootsuffix|启动[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]使用备用位置。 通过创建的快捷方式通过运行以下命令[!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)]安装程序：<br /><br /> devenv /RootSuffix exp<br /><br /> 在这种情况下，exp 标识具有特定的后缀，例如 10.0Exp 而不是 10.0 的位置。 实验实例中，你可以调试分开的实例的 VSPackage[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]用来编写代码。<br /><br /> 此开关可以接受任何字符串，标识已使用 VSRegEx.exe 创建的位置。 有关详细信息，请参阅[实验实例](../extensibility/the-experimental-instance.md)。|  
|/splash|显示[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]像往常一样初始屏幕，然后显示在主 IDE 前显示一个消息框。 消息框，您研究初始屏幕中，若要检查 VSPackage 产品图标，例如。<br /><br /> 此开关不带参数。|  
  
## <a name="see-also"></a>请参阅  
 [添加命令行开关](../extensibility/adding-command-line-switches.md)   
 [Devenv 命令行开关](../ide/reference/devenv-command-line-switches.md)