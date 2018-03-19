---
title: "在 Visual Studio 中安装和配置测试代理 | Microsoft Docs"
ms.date: 03/02/2018
ms.technology: vs-devops-test
ms.topic: article
helpviewer_keywords:
- configure test agents, test lab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 16e29676ec67bc3fd22313debe70ba8dbcd7fd76
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="install-and-configure-test-agents"></a>安装和配置测试代理

对于使用 Visual Studio 和 Visual Studio Team Services (VSTS) 或 Team Foundation Server (TFS) 的测试方案，无需测试控制器。 Visual Studio 的代理通过与 VSTS 或 TFS 通信来处理业务流程。 一种情况可能是你在 VSTS 或 TFS 中运行用于生成和发布工作流的连续测试。

还可考虑[改为使用 Build Management 或 Release Management ](use-build-or-rm-instead-of-lab-management.md)来替代实验室管理是否会更好。

## <a name="system-requirements"></a>系统要求

| 项 | 惠? |
| ---- | ------------ |
| **代理** | Windows 10<br />Windows 8、Windows 8.1<br />Windows 7 Service Pack 1<br />Windows XP Service Pack 3<br />Windows Server 2012、Windows Server 2012 R2<br />Windows Server 2008 Release 2，Service Pack 1 |
| **控制器** | Windows 10<br />Windows 8、Windows 8.1<br />Windows 7 Service Pack 1<br />Windows Server 2012、Windows Server 2012 R2<br />Windows Server 2008 Release 2，Service Pack 1 |
| **.NET Framework** | .NET Framework 4.5 |

## <a name="install-the-test-controller-and-test-agents"></a>安装测试控制器和测试代理

可从 [visualstudio.com](https://www.visualstudio.com/downloads/?q=agents) 中下载 Visual Studio 2017 的代理。查找 Visual Studio 2017 的代理，然后选择“代理”或“控制器”。 可以从[早期下载](https://www.visualstudio.com/vs/older-downloads/)页中下载 Visual Studio 2015 和 Visual Studio 2013 的代理。

这些安装程序可用作 ISO 文件，便于在虚拟机上安装。

## <a name="compatible-versions-of-tfs-microsoft-test-manager-the-test-controller-and-test-agent"></a>TFS、Microsoft 测试管理器、测试控制器和测试代理的兼容版本

可以根据下表混合使用不同版本的 TFS、Microsoft 测试管理器 (MTM)、测试控制器和测试代理：

| TFS | 使用实验室中心的 MTM | 控制器 | 代理 |
| --- | -------------------------------------- | ---------- | ----- |
| 2017：从 2015 升级或全新安装 | 2017 | 2017 | 2017 |
| 2017：从 2015 升级或全新安装 | 2017 | 2013 Update 5 | 2013 Update 5 |
| 2017：从 2015 升级或全新安装 | 2015 | 2013 Update 5 | 2013 Update 5 |
| 2015：从 2013 升级 | 2013 | 2013 |2013 |
| 2015：全新安装 | 2013 | 2013 | 2013 |
| 2015：从 2013 升级或全新安装 | 2015 | 2013 | 2013 |
| 2013 | 2015 | 2013 | 2013 |

## <a name="upgrade-from-visual-studio-2013-test-agents"></a>从 Visual Studio 2013 测试代理升级

建议在所有新的自动测试方案中都使用 Visual Studio 的代理。 可以在生成定义中使用“部署测试代理”任务在计算机上下载和安装测试代理。

下表显示了 Agents for Visual Studio 2013 支持的方案，以及 Team Foundation Server (TFS) 2015 和 VSTS 的替代方案：

| Agents for Visual Studio 2013 支持的方案 | TFS 和 VSTS 中的替代方案 |
| --- | --- |
| Visual Studio 中的“生成-部署-测试工”作流 | 用户可以在 TFS 中使用[生成定义](/vsts/build-release/)（而不是 XAML 生成）生成、部署和测试方案。 |
| 使用本地远程计算机进行负载测试（性能测试） | 使用 Test Controller 和 Test Agents 2013 Update 5 在本地运行负载测试。 有关详细信息，请参阅[在负载测试中使用测试控制器和测试代理](https://msdn.microsoft.com/library/ff400223.aspx)。 |
| 使用实验室环境从 Microsoft 测试管理器远程执行自动测试 | 目前此方案没有替代方案。 建议在生成和发布定义（而不是 XAML 生成）中使用“运行功能测试”任务来远程执行测试。 |
| 开发人员在 Visual Studio 中执行远程测试 | 不再支持。 |

## <a name="see-also"></a>请参阅

* [设置计算机和收集诊断信息](https://msdn.microsoft.com/library/dd286743%28v=vs.140%29.aspx)
