---
title: 将 Python 应用发布到 Azure 应用服务
description: 如何将 Python Web 应用程序从 Visual Studio 直接发布到 Azure 应用服务，包括 web.config 文件必需的内容。
ms.date: 09/27/2017
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
ms.openlocfilehash: 4e8d28bb96fa17a82d758f5708fd592128296e7d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="publishing-to-azure-app-service"></a>发布到 Azure 应用服务

Visual Studio 提供将 Python Web 应用直接发布到 Azure 应用服务的功能。 发布到 Azure App Service 意味着将所需文件复制到服务器，并设置相应的 `web.config` 文件来指示 Web 服务器如何启动应用。

Visual Studio 2017 与 Visual Studio 2015 的发布过程有所不同。 具体而言，Visual Studio 2015 自动执行某些步骤，包括创建 `web.config`，但这种自动化会限制长期的灵活性和控制。 Visual Studio 2017 需要更多手动步骤，但对 Python 环境提供更精确的控制。 此处对这两个选项均有介绍。

> [!Note]
> 有关 Visual Studio 2015 与 Visual Studio 2017 之间的变化的背景信息，请参阅博客文章 [Publish to Azure in Visual Studio 2017](https://blogs.msdn.microsoft.com/pythonengineering/2016/12/12/publish-to-azure-in-vs-2017/)（在 Visual Studio 2017 中发布到 Azure）。

## <a name="prerequisites"></a>系统必备

在本演练中，需要一个基于 Bottle、Flask 或 Django 框架的 Web 应用项目。 如果还没有项目，但想尝试发布过程，可按下面所示创建一个简单的测试项目：

1. 在 Visual Studio 中，选择“文件”>“新建”>“项目”，搜索“Bottle”，选择“Bottle Web 项目”，为项目指定名称和路径，然后单击“确定”。 （Bottle 模板随附于 Python 开发工作负载中；请参阅[安装](installing-python-support-in-visual-studio.md)。）

1. 按提示安装外部程序包，并选择“安装到虚拟环境”和虚拟环境的首选基础解释器。 通常需要将此选项与 App Service 上安装的 Python 版本匹配。

1. 按 F5 或选择“调试”>“开始调试”，在本地测试项目。

## <a name="create-an-azure-app-service"></a>创建 Azure App Service

发布到 Azure 需要一个目标 App Service。 为此，可使用 Azure 订阅创建一个 App Service，也可使用临时站点。

如果还没有订阅，则以[免费的完整 Azure 帐户](https://azure.microsoft.com/free/)入手，该帐户提供丰厚的 Azure 服务信用额度。 此外，请考虑注册 [Visual Studio Dev Essentials](https://azure.microsoft.com/pricing/member-offers/vs-dev-essentials/)，每个月提供 25 美元信用额度，为期一年。

> [!Tip]
> 虽然 Azure 要求提供信用卡来验证帐户，但不会向该卡收费。 用户也可以将[支出限制](/azure/billing/billing-spending-limit)设置为等于可用信用额度，确保不会被收取额外的费用。 此外，Azure 还提供应用服务计划免费层，非常适合下一部分所述的简单测试应用。

### <a name="using-a-subscription"></a>使用订阅

使用有效的 Azure 订阅，创建一个包含空 Web 应用的 App Service，如下所示：

1. 登录 [portal.azure.com](https://portal.azure.com)。
1. 选择“+新建”，然后依次选择“Web + 移动”、“Web 应用”。
1. 指定 Web 应用的名称，将“资源组”保留为“新建”，并选择“Windows”作为操作系统。
1. 选择“应用服务计划/位置”，选择“新建”，并指定名称和位置。 然后选择“定价层”，向下滚动到“F1 免费”计划并选择该计划，依次按“选择”、“确定”、“创建”。
1. （可选）创建 App Service 后，导航到该服务，选择“获取发布配置文件”，并将文件保存在本地。

### <a name="using-a-temporary-app-service"></a>使用临时 App Service

在没有 Azure 订阅的情况下创建临时 App Service，如下所示：

1. 打开浏览器浏览 [try.azurewebsites.net](https://try.azurewebsites.net)。
1. 选择“Web 应用”应用类型，然后选择“下一步”。
1. 依次选择“空站点”、“创建”。
1. 使用所选社交登录名登录，不久后站点会在所显示的 URL 处准备就绪。
1. 选择“下载发布配置文件”并保存 `.publishsettings` 文件，稍后会使用该文件。

## <a name="configure-python-on-azure-app-service"></a>在 Azure App Service 上配置 Python

在订阅或免费站点上创建运行空 Web 应用的 App Service 后，如[在 Azure App Service 上管理 Python](managing-python-on-azure-app-service.md) 中所述安装选定的 Python 版本。 若要从 Visual Studio 2017 进行发布，则如该文所述，记录随站点扩展一起安装的 Python 解释器的确切路径。

如果需要，还可以按照这些说明中的过程安装 `bottle` 程序包，因为在执行本演练的其他步骤时也会安装该程序包。

## <a name="publish-to-app-service---visual-studio-2017"></a>发布到 App Service - Visual Studio 2017

从 Visual Studio 2017 发布到 Azure App Service 时，仅将项目中的文件复制到服务器。 因此，必须创建所需的文件才能配置服务器环境。

1. 在 Visual Studio 的“解决方案资源管理器”中，右键单击项目，选择*“添加”>“新项...”。在随即出现的对话框中，选择“Azure web.config (Fast CGI)”模板并选择“确定”。 这会在项目根目录中创建 `web.config` 文件。

1. 修改 `web.config` 中的 `PythonHandler` 条目，使路径与服务器上安装的 Python 相匹配。 例如，对于 Python 3.6.1 x64，该条目应如下所示：

    ```xml
    <system.webServer>
      <handlers>
        <add name="PythonHandler" path="*" verb="*" modules="FastCgiModule"
            scriptProcessor="D:\home\Python361x64\python.exe|D:\home\Python361x64\wfastcgi.py"
            resourceType="Unspecified" requireAccess="Script"/>
      </handlers>
    </system.webServer>
    ```

1. 设置 `web.config` 中的 `WSGI_HANDLER` 条目，以适合正在使用的框架：

    - **Bottle**：在 `app.wsgi_app` 后面添加括号，如下所示。 此操作是必需的，因为该对象是函数（请参阅 `app.py`）而非变量：

        ```xml
        <!-- Bottle apps only -->
        <add key="WSGI_HANDLER" value="app.wsgi_app()"/>
        ```

    - **Flask**：将 `WSGI_HANDLER` 值更改为 `<project_name>.app`，其中 `<project_name>` 与项目名称匹配。 可通过查看 `runserver.py` 中的 `from <project_name> import app` 语句，找到准确的标识符。 例如，如果项目命名为“FlaskAzurePublishExample”，则该条目如下所示：

        ```xml
        <!-- Flask apps only: change the project name to match your app -->
        <add key="WSGI_HANDLER" value="FlaskAzurePublishExample.app"/>
        ```

    - **Django**：对于 Django 应用，需要对 `web.config` 进行两项更改。 首先，将 `WSGI_HANDLER` 值更改为 `django.core.wsgi.get_wsgi_application()`（该对象位于 `wsgi.py` 文件中）：

        ```xml
        <!-- Django apps only -->
        <add key="WSGI_HANDLER" value="django.core.wsgi.get_wsgi_application()"/>
        ```

        其次，在 `WSGI_HANDLER` 条目下添加以下条目，并将 `DjangoAzurePublishExample` 替换为项目名称：

        ```xml
        <add key="DJANGO_SETTINGS_MODULE" value="DjangoAzurePublishExample.settings" />
        ```

1. **仅限 Django 应用**：在与项目名称匹配的文件夹中，打开 `settings.py`，按下面所示将站点 URL 域添加到 `ALLOWED_HOSTS`，当然，要将“vspython-test-02.azurewebsites.net”替换为自己的 URL：

    ```python
    # Change the URL to your specific site
    ALLOWED_HOSTS = ['vspython-test-02.azurewebsites.net']
    ```

    未能将 URL 添加到该阵列会导致出现错误“DisallowedHost at / Invalid HTTP_HOST 标头:‘\<站点 URL\>’。 可能需要将‘\<站点 URL\>’添加到 ALLOWED_HOSTS。”

1. 在“解决方案资源管理器”中，展开与项目同名的文件夹，右键单击 `static` 文件夹，选择“添加”>“新项...”，选择“Azure 静态文件 web.config”模板，然后选择“确定”。 此操作会在 `static` 文件夹中创建另一个 `web.config`，以禁止 Python 处理该文件夹。 此配置将静态文件请求发送到默认 Web 服务器，而不是使用 Python 应用程序。

1. 保存项目，然后在 Visual Studio 的“解决方案资源管理器”中，右键单击项目并选择“发布”。

1. 在随即出现的“发布”选项卡中，选择发布目标：

    a. 用户自己的 Azure 订阅：选择“Microsoft Azure App Service”，然后依次选择“选择现有”、“发布”。 随即显示一个对话框，可在其中选择相应的订阅和 App Service。 如果未显示 App Service，则按下面所述，将下载的发布配置文件用于临时 App Service。

    ![发布到 Azure 步骤 1, Visual Studio 2017, 现有订阅](media/tutorials-common-publish-1a-2017.png)

    b. 如果正在 try.azurewebsites.net 上使用临时 App Service，或在其他情况下需要使用发布配置文件，则选择 **>** 控件查找“导入配置文件”，选择该选项，然后选择“发布”。 这会提示输入之前下载的 `.publishsettings` 文件的位置。

    ![发布到 Azure 步骤 1, Visual Studio 2017, 临时 App Service](media/tutorials-common-publish-1b-2017.png)

1. Visual Studio 在“Web 发布活动”窗口和“发布”窗口中显示发布状态。 完成发布后，会在站点 URL 上打开默认浏览器。 该 URL 也显示在“发布”窗口中。

1. 浏览器打开后，可能会显示消息“无法显示页面，因为发生内部服务器错误。” 此消息表示服务器上的 Python 环境未完全配置，此时应执行以下步骤：

    a. 请再次参阅[在 Azure App Service 上管理 Python](managing-python-on-azure-app-service.md)，确保安装了相应的 Python 站点扩展。

    b. 仔细检查 `web.config` 文件中的 Python 解释器路径。 该路径必须与所选站点扩展的安装位置完全匹配。

    c. 使用 Kudu 控制台对应用的 `requirements.txt` 文件中列出的所有程序包进行升级：导航到 `web.config` 中使用的相同 Python 文件夹（比如 `/home/python361x64`），并运行 [Kudu 控制台](managing-python-on-azure-app-service.md#azure-app-service-kudu-console)部分中所述的以下命令：

    ```command
    python -m pip install --upgrade -r /home/site/wwwroot/requirements.txt
    ```

    如果运行此命令时显示权限错误，请仔细检查，确保是在站点扩展文件夹中运行此命令，而*不是*在 App Service 的某个默认 Python 安装文件夹中运行此命令。 由于你无法修改这些默认环境，因此尝试安装程序包当然会失败。

    d. 若要获取详细的错误输出，请向 `<system.webServer>` 节点中的 `web.config` 添加以下行，以提供更详细的错误输出：

    ```xml
    <httpErrors errorMode="Detailed"></httpErrors>
    ```

    e. 安装新程序包后，尝试重新启动 App Service。 更改 `web.config` 时不必重新启动，因为一旦 `web.config` 更改，App Service 就会自动重新启动。

    > [!Tip] 
    > 如果对应用的 `requirements.txt` 文件进行任何更改，请确保再次使用 Kudu 控制台安装该文件现在列出的所有程序包。 

1. 完全配置服务器环境后，刷新浏览器中的页面，应该会显示 Web 应用。

    ![将 Bottle、Flask 和 Django 应用发布到 App Service 的结果](media/azure-publish-results.png)

## <a name="publishing-to-app-service---visual-studio-2015"></a>发布到 App Service - Visual Studio 2015

> [!Note] 
> 在 [Visual Studio Python Tutorial: Building a Website](https://www.youtube.com/watch?v=FJx5mutt1uk&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff&index=6)（Visual Studio Python 教程：生成网站，youtube.com，3 分 10 秒）上可找到此过程的简短视频。

1. 在“解决方案资源管理器”中，右键单击项目，选择“发布”。

1. 在“发布”对话框中，选择“Microsoft Azure 应用服务”：

  ![发布到 Azure 步骤 1](media/tutorials-common-publish-1.png)

1. 选择目标：

    - 如果具有 Azure 订阅，请选择“Microsoft Azure 应用服务”作为发布目标，然后在以下对话框中，选择一个现有应用服务或选择“新建”新建一个。
    - 如果从 try.azurewebsites.net 使用临时站点，请选择“导入”作为发布目标，然后浏览从该站点下载的 `.publishsettings` 文件，再选择“确定”。

1. 应用服务详细信息显示在下面的“发布”对话框的“连接”选项卡中。

  ![发布到 Azure 步骤 2](media/tutorials-common-publish-2.png)

1. 根据需要选择“下一步 >”，查看其他设置。 如果计划[在 Azure 上远程调试 Python 代码](debugging-remote-python-code-on-azure.md)，必须将“配置”设置为“调试”

1. 选择“发布”。 应用程序部署到 Azure 后，会在该站点上打开默认浏览器。 

在此过程中，Visual Studio 还执行以下步骤：

- 在包含指向应用 `wsgi_app` 函数和 App Service 默认 Python 3.4 解释器的相应指针的服务器上，创建 `web.config` 文件。
- 关闭对项目 `static` 文件夹中文件的处理（此步骤的规则位于 `web.config` 中）。
- 将虚拟环境发布到服务器。
- 添加 `web.debug.config` 文件和 ptvsd 调试工具以启用远程调试。

如前文所述，这些自动步骤可简化发布过程，但会使其更难控制 Python 环境。 例如，仅在服务器上创建 `web.config` 文件，但不将它添加到项目中。 发布过程也较长，因为它是从开发计算机复制整个虚拟环境，而不依赖于服务器配置。

最终，用户可能会想维护自己的 `web.config` 文件，并使用 `requirements.txt` 直接在服务器上维护程序包。 特别指出的是，使用 `requirements.txt` 可确保开发环境和服务器环境始终匹配。

## <a name="remote-debugging-on-azure-app-service"></a>在 Azure App Service 上进行远程调试

从 Visual Studio 2015 发布调试配置时，该过程会自动创建 `web.debug.config` 文件，并添加一个包含必要调试工具的 `ptvsd` 文件夹。

而使用 Visual Studio 2017 时，会将这些组件直接添加到项目中。 在“解决方案资源管理器”中右键单击项目，选择“添加”>“新项...”，然后选择“Azure 远程调试 web.config”模板。 项目中会出现调试 `web.debug.config` 文件和 `ptvsd` 工具文件夹。

将这些文件部署到服务器（使用 Visual Studio 2015 时自动部署；使用 Visual Studio 2017 时在下一次发布时部署）后，可以按照 [Azure 远程调试](debugging-remote-python-code-on-azure.md)相关说明操作。
