---
title: Python 项目的项模板
description: 可通过 Visual Studio 中的“添加”>“新项”对话框来获取 Python 项目项模板的引用列表。
ms.date: 04/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 5bbfab8cac4050477686695ccb14c37d76cbf376
ms.sourcegitcommit: 0cf1e63b6e0e6a0130668278489b21a6e5038084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2018
ms.locfileid: "39469344"
---
# <a name="python-item-templates"></a>Python 项模板

Python 项目中的项模板可通过“项目” > “添加新项”菜单命令获取，也可以通过“解决方案资源管理器”上下文菜单中的“添加” > “新项”命令获取。

![“添加新项”对话框](media/project-item-templates.png)

通过使用为项目提供的名称，模板通常会在项目当前选定的文件夹中创建一个或多个文件和文件夹（右键单击一个文件夹以打开上下文菜单会自动选择该文件夹）。 添加一个项会将其包含在 Visual Studio 项目中，并且该项会显示在“解决方案资源管理器”中。

下表简要说明了 Python 项目中每个项模板的效果：

| 模板 | 模板创建的内容 |
| --- | --- |
| 空 Python 文件 | 具有 .py 扩展名的空文件。 |
| Python 类 | 包含单个空 Python 类定义的 .py 文件。 |
| Python 包 | 包含 \_\_init\_\_.py 文件的文件夹。 |
| Python 单元测试 | 一个 .py 文件，包含基于 `unittest` 框架的单个单元测试，以及用于在文件中运行测试的对 `unittest.main()` 的调用。 |
| HTML 页 | 一个 .html 文件，其简单页结构由 `<head>` 和 `<body>` 元素组成。 |
| JavaScript | 一个空的 .js 文件。 |
| 样式表 | 包含 `body` 空样式的 .css 文件。 |
| 文本文件 | 一个空的 .txt 文件。 |
| Django 1.9 应用<br/>Django 1.4 应用 | 一个使用应用名称的文件夹，它包含 Django 应用的核心文件，如 Django 1.9 [了解 Visual Studio 中的 Django，步骤 2-2](learn-django-in-visual-studio-step-02-create-an-app.md#step-2-1-create-an-app-with-a-default-structure)中所述。 对于 Django 1.4，不包括“迁移”文件夹、admin.py 文件和 apps.py 文件。 |
| IronPython WPF 窗口 | WPF 窗口包含两个并排显示的文件：使用空 `<Grid>` 元素定义 `<Window>` 的 .xaml 文件，和使用 `wpf` 库加载 XAML 文件的关联 .py 文件。 通常在使用某一 IronPython 项目模板创建的项目中使用。 请参阅[管理 Python 项目 - 项目模板](managing-python-projects-in-visual-studio.md#project-templates)。 |
| Web 角色支持文件 | 项目根目录中的 bin 文件夹（不考虑项目中所选的文件夹）。 文件夹包含默认部署脚本和 Azure 云服务 Web 角色的 web.config 文件。 模板还包含介绍了详细说明的 readme.html 文件。 |
| 辅助角色支持文件 | 项目根目录中的 bin 文件夹（不考虑项目中所选的文件夹）。 该文件夹包含默认部署和启动脚本，以及针对 Azure 云服务辅助角色的 web.config 文件。 模板还包含介绍了详细说明的 readme.html 文件。 |
| Azure web.config (FastCGI) | 包含应用条目的 web.config 文件，这些应用使用 [WSGI](https://wsgi.readthedocs.io/en/latest/) 对象来处理传入的连接。 此文件通常部署到运行 IIS 的 Web 服务器的根目录中，例如 Azure 应用服务。 有关详细信息，请参阅[发布到 Azure 应用服务](publishing-python-web-applications-to-azure-from-visual-studio.md)。 |
| Azure web.config (HttpPlatformHandler) | 包含应用条目的 web.config 文件，这些应用侦听套接字的传入连接。 此文件通常部署到运行 IIS 的 Web 服务器的根目录中，例如 Azure 应用服务。 有关详细信息，请参阅[发布到 Azure 应用服务](publishing-python-web-applications-to-azure-from-visual-studio.md)。 |
| Azure 静态文件 web.config | 一个 web.config 文件，通常被添加到“静态”文件夹（或包含静态项的其他文件夹）以禁止 Python 处理该文件夹。 此配置文件与上面其中一个 FastCGI 或 HttpPlatformHandler 配置文件结合使用。 有关详细信息，请参阅[发布到 Azure 应用服务](publishing-python-web-applications-to-azure-from-visual-studio.md)。 |
| Azure 远程调试 web.config | 一个 web.config.debug 文件，它支持通过 WebSocket 进行远程调试，另外还有“Microsoft.PythonTools.WebRole.dll”和“ptvsd”文件夹，其中包含要部署到服务器以支持远程调试的模块。 通常在与 web.config 文件相同的位置创建此项目。 有关详细信息，请参阅[在 Azure 上远程调试 Python 代码](debugging-remote-python-code-on-azure.md)。 另请参阅下面的说明。 |

> [!Note]
> 如果将调试 web.config 模板添加到项目并计划使用 Python 远程调试，需要在“调试” 配置中发布站点。 此设置独立于当前的活动解决方案配置，且始终默认为“发布”。 若要更改它，请打开“设置”选项卡，并使用“发布”向导中的“配置”组合框。 （有关创建和部署到 Azure Web 应用的详细信息，请参阅 [Azure 文档](https://azure.microsoft.com/develop/python/)。）
>
> ![更改发布配置](media/template-web-publish-config.png)

### <a name="see-also"></a>请参阅

- [管理 Python 项目 - 项目模板](managing-python-projects-in-visual-studio.md#project-templates)
- [Python Web 项目模板](python-web-application-project-templates.md)
- [发布到 Azure 应用服务](publishing-python-web-applications-to-azure-from-visual-studio.md)