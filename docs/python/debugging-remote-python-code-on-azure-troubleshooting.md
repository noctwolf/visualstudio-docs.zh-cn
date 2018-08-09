---
title: 适用于 Python 的 Azure 远程调试疑难解答
description: 如何解决在尝试使用 Visual Studio 对 Azure 应用服务中运行的 Python 应用程序进行调试时遇到的问题。
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: f545fa223aa929b79016352e799d112bceddaf1c
ms.sourcegitcommit: 4f82c178b1ac585dcf13b515cc2a9cb547d5f949
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341458"
---
# <a name="remote-debugging-troubleshooter-for-python-and-azure"></a>适用于 Python 和 Azure 的远程调试故障排除程序

由于下列任意原因，Visual Studio 将而无法附加到 [Azure App Service 进行远程调试](debugging-remote-python-code-on-azure.md)：

| 原因 | 解决方法 |
| --- | --- |
| 未安装 Visual Studio 2013 Update 4 或更高版本。 | 通过 [visualstudio.microsoft.com](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 安装合适的版本。 |
| 部署到应用服务的项目与 Visual Studio 中打开的不匹配。 | 将正确的项目加载到 Visual Studio。 |
| 项目未使用“调试”配置进行部署。 | 右键单击解决方案资源管理器中的项目并选择“发布”，重新部署应用程序。 在“设置”选项卡中，确保“调试”是所选的配置。 |
| 应用服务未在运行。 | 从 Visual Studio 中的服务器资源管理器或 Azure 门户启动它。 |
| 应用服务未针对 Web 套接字进行配置。 | 转到[“Azure 门户”](https://portal.azure.com)，导航到应用服务，打开“设置” > “应用程序设置”，将“常规设置” > “Web 套接字”切换为“打开”，然后选择“保存”。 （请注意，此边栏选项卡上显示的“调试”选项*不*适用于 Python 调试。） |
| 已修改 web.debug.config 以禁用调试代理。 | 删除文件并将项目重新发布到应用服务，在此期间，Visual Studio 将重新创建该文件。 |

另请参阅：

- [针对 Python 的 Azure 远程调试](debugging-remote-python-code-on-azure.md)
