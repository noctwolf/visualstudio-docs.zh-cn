---
title: 为 ASP.NET 应用程序启用调试 |Microsoft Docs
ms.custom: H1HackMay2017
ms.date: 09/21/17
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging ASP.NET Web applications
- Web.config configuration file, debug mode
- debugging [Visual Studio], ASP.NET
ms.assetid: 3beed819-cece-4864-8184-bd410000973a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 438e5a96ef07faf399d06ae517afe313a44673b4
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057845"
---
# <a name="debug-aspnet-applications-in-visual-studio"></a>调试 Visual Studio 中的 ASP.NET 应用程序

您可以调试 ASP.NET 应用程序从 Visual Studio。

## <a name="requirements"></a>要求

若要遵循本主题中的说明进行操作，需要：

- IIS Express，它包括默认情况下，在 Visual Studio 2012 及更高版本

    或

- 本地 IIS web 服务器 （版本 8.0 或更高版本） 的配置正确并且可以运行 ASP.NET 应用程序未出现错误。

如果远程服务器，则必须在远程计算机上运行远程调试器。 若要在远程 IIS 服务器上进行调试，请参阅[IIS 计算机上的远程调试 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)。 

## <a name="configure-debug-settings"></a>配置调试设置

### <a name="enable-aspnet-debugging-in-the-project-properties"></a>项目属性中启用 ASP.NET 调试

1. 在 Visual Studio 中打开 ASP.NET 项目。

2. 右键单击该项目中的**解决方案资源管理器**，选择**属性**，然后单击**Web**选项卡。

    对于某些项目类型，选择**属性 > 调试**相反。 对于 ASP.NET Web 窗体项目，右键单击项目并选择**属性页 > 启动选项**。
  
3.  在“调试器” 下，选中“ASP.NET”  复选框。

    ![调试器设置](../debugger/media/dbg-aspnet-enable-debugging.png "调试器设置")

> [!NOTE]
> 如果创建新的 ASP.NET 项目 (**文件 > 新建项目**)，调试设置已正确配置。

### <a name="enable-debugging-in-the-webconfig-file"></a>Web.config 文件中启用调试  

若要调试的 web 应用，必须正确配置应用程序的 web.config 文件。 如果你托管在 IIS 或 IIS Express 应用程序，则需要 web.config 文件。

对于 ASP.NET Core 应用程序部署 （如果该帐户不存在） 时自动创建 web.config 文件。

> [!TIP]
> 在部署过程可能会更新 web.config 设置。 因此在尝试调试之前, 验证服务器上的 web.config 设置。
  
1.  在 Visual Studio 中，打开项目的 web.config 文件。  
  
    > [!NOTE]  
    > 不能使用 Web 浏览器的远程访问 web.config 文件。 出于安全原因，[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]配置 Microsoft IIS，以帮助防止对 Web.config 文件直接浏览器访问。 如果你尝试使用浏览器访问配置文件，你会获得 HTTP 访问错误 403 （禁止访问）。  
  
2.  查找 `configuration/system.web/compilation` 元素。 如果 compilation 元素不存在，则创建它。

    Web.config 是一个 XML 文件，因此包含使用标记来标记的嵌套节。
  
3.  如果 `compilation` 元素不包含 `debug` 特性，请向元素添加该特性。  
  
4.  确保 `debug` 特性值设置为 `true`。  
  
Web.config 文件应如以下示例所示：

> [!NOTE]
> 此示例是分部的 web.config 文件。 Configuration 和 system.web 元素之间通常存在 XML 的其他部分。 Compilation 元素还可能包含其他属性和元素。
  
#### <a name="example"></a>示例  
  
```xml
<configuration>  
    ...  
    <system.web>  
        <compilation  
            debug="true"  
            ...  
        >  
        ...  
        </compilation>  
    </system.web>  
</configuration>  
```

如果您使用外部服务器而不默认 IIS Express 服务器，您必须还确保`targetFramework`属性值与服务器上的配置相匹配。

> [!IMPORTANT]
> 为了获得最佳性能，设置生产应用为`debug=false`和指定的版本生成时生成和发布应用程序。

## <a name="configure-project-settings-for-the-server"></a>配置服务器的项目设置

对于本地 web 服务器上的调试，设置项目属性。 对于远程服务器上的调试，请按照中所述的更全面说明[Remote Debugging ASP.NET on IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)相反。

1. 在**Web**选项卡上的项目属性中，选择任一**IIS Express**或**外部服务器**下**Server**设置。 (对于某些项目类型，这些设置将显示下**调试**改为选项卡。)

    ![服务器设置](../debugger/media/dbg-aspnet-server-settings.png "服务器设置")

    IIS Express 用于 ASP.NET 的默认服务器中，通常不需要任何特殊配置。 这是调试 ASP.NET 应用程序的最简单方法。

    对于 ASP.NET Web 窗体项目，右键单击该项目中，选择**属性页 > 启动选项**，然后选择**使用默认 Web 服务器**或**使用自定义服务器**(而不是**外部服务器**)。

    ![Web 窗体应用程序的服务器设置](../debugger/media/dbg-aspnet-server-settings-webforms.png "Web 窗体应用程序的服务器设置")

2. 如果您选择的外部 （自定义） 服务器，输入中的正确 URL**项目 URL** (或**基 URL**) 字段。

    如果外部服务器是本地 IIS，则必须安装 IIS，并将其正确配置。 例如，必须在 IIS 中配置正确版本的 ASP.NET。 有关详细信息，请参阅[IIS 8.0 使用 ASP.NET 3.5 和 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)。 如果你想要测试部署以及调试，请参阅[部署测试](/aspnet/web-forms/overview/deployment/visual-studio-web-deployment/deploying-to-iis)。

    外部服务器是否[远程](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)相反，附加到进程，这些项目设置不用于调试。

## <a name="local-iis-web-server-configure-iis"></a>（本地 IIS web 服务器）配置 IIS

对于 IIS Express，您无需配置 web 服务器 （跳过此部分）。 对于初始测试，建议使用 IIS Express。

如果使用本地 IIS web 服务器，请执行以下步骤。

1. 请确保正确安装 IIS。 有关详细信息，请参阅[IIS 8.0 使用 ASP.NET 3.5 和 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)。

    * 请确保在服务器上安装正确版本的 ASP.NET。 使用 Web 平台安装程序 (WebPI) 安装 ASP.NET 4.5 (从 Windows Server 2012 R2 中的服务器节点，选择**获取新的 Web 平台组件**，然后搜索 ASP.NET)。 若要安装 ASP.NET Core，请参阅[发布到 IIS](https://docs.asp.net/en/latest/publishing/iis.html#iis-configuration)。

    > [!NOTE]
    > 如果使用 Windows Server 2008 R2，安装 ASP.NET 4 改为使用此命令：

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. 打开**Internet Information Services (IIS) 管理器**。 (在服务器管理器的左窗格中，选择**IIS**。 右键单击服务器，然后选择**Internet 信息服务 (IIS) 管理器**。)

3. 下**连接**在左窗格中，转到**站点**。

4. 右键单击“默认网站”  节点，然后选择“添加应用程序” 。

5. 设置**别名**字段**MyASPApp**，接受默认应用程序池 (**DefaultAppPool**)，并设置**物理路径**到**C:\inetpub\myNewFolder** （创建应用程序的新文件夹）。

6. 下**连接**，选择**应用程序池**。 打开**DefaultAppPool**并将应用程序池字段设置为的值是正确的应用程序 （使用 ASP.NET 4 为 ASP.NET 4.5。 使用**无托管的代码**为 ASP.NET Core)。

## <a name="local-iis-web-server-deploy-the-app"></a>（本地 IIS web 服务器）将应用部署

IIS express，web 应用自动部署在开始调试时 （跳过此部分）。

如果使用本地 IIS web 服务器，请执行以下步骤。 有不同的方式来将应用发布到 IIS。 在这些步骤中，我们演示如何创建和使用发布配置文件，以便可以使用文件系统进行部署。

1. 以管理员身份重新启动 Visual Studio。

    若要使用此方法进行部署，需要管理员权限。

2. 在 Visual Studio 中，右键单击该项目并选择**发布**(对于 Web 窗体，使用**发布 Web 应用**)。

3. 选择**IIS、 FTP 等**然后单击**发布**。

    ![将发布到 IIS](../debugger/media/dbg-aspnet-local-iis.png "将发布到 IIS")

    对于 Web 窗体应用中，选择**自定义**在发布对话框中，输入配置文件名称，然后选择**确定**。

4. 在中**发布方法**字段中，选择**文件系统**。

5. 有关**目标位置**，单击**浏览**按钮。

6. (ASP.NET Core)选择**文件系统**并选择在之前创建的应用程序的文件夹。

6. (ASP.NET)选择**本地 IIS**，然后选择 web 站点之前创建，然后依次**打开**。

    ![将发布到 IIS](../debugger/media/dbg-aspnet-local-iis-select-site.png "将发布到 IIS")

    > [!TIP]
    > 如果您看到一条消息，指出 web 服务器配置不正确，请确保为 IIS 安装正确版本的 ASP.NET。

7. 单击**下一步**，然后选择**调试**配置。

    > [!NOTE]
    > 如果部署时使用发布配置，这将设置`debug=false`服务器的 web.config 文件中。

8. 单击**保存**以保存发布设置，然后单击**发布**。

    > [!CAUTION]
    >  如果需要更改代码或重新生成，必须重新发布并重复此步骤。 复制到远程计算机的可执行文件必须与你的本地源和符号完全匹配。

## <a name="set-a-breakpoint-and-start-debugging"></a>设置断点并开始调试

1. 在 Visual Studio 中的项目，将运行在您知道一些代码设置一个断点。

2. 若要开始调试，按**F5** (**调试 > 启动调试**)。

3. 采取操作来运行包含断点的代码。

    调试器暂停设置了断点。

### <a name="local-iis-troubleshooting-cannot-hit-the-breakpoint"></a>(本地 IIS)故障排除： 无法命中断点

1. 从 IIS 启动 web 应用并确保它能够正常运行。 将运行的 web 应用。

2. 从 Visual Studio 中，选择**调试 > 附加到进程**并连接到 ASP.NET 进程 (通常**w3wp.exe**或**dotnet.exe**)。 有关详细信息，请参阅[附加到进程](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)。

    如果可以使用进行连接**附加到进程**，可以命中断点，但不能启动使用调试**F5**，则很可能设置不正确的项目属性中。 如果使用的主机文件，请验证已正确配置。

  
## <a name="robust-programming"></a>可靠编程  
[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 自动检测对 Web.config 文件的任何更改，并应用新的配置设置。 不必重新启动计算机或 IIS 服务器，更改即可生效。  
  
一个网站可包含多个虚拟目录和子目录，而 Web.config 文件可能存在于每个目录中。 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 应用程序从 URL 路径中的更高级别的 Web.config 文件中继承设置。 分层配置文件允许您更改多个设置[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]在同一时间，例如，针对层次结构中其下的所有应用程序的应用程序。 但是，如果`debug`设置在层次结构中较低级别文件中，它将替代较高的值。  
  
例如，可以指定`debug="true"`在 www.microsoft.com/aaa/Web.config，并且 aaa 文件夹中或在任何应用程序的 aaa 的任何子文件夹继承该设置。 因此，如果你[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]应用程序位于 www.microsoft.com/aaa/bbb，它将继承该设置，如将任何[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]www.microsoft.com/aaa/ccc 和 www.microsoft.com/aaa/ddd，等等的应用程序。 唯一的例外情况是其中一个应用程序通过自己的较低级的 Web.config 文件提替代设置。  
  
> [!IMPORTANT]
> 启用调试模式下，极大地影响性能的你[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]应用程序。 请记住，在部署发布版本的应用程序或进行性能度量之前要禁用调试模式。  
  
## <a name="see-also"></a>请参阅  
[ASP.NET 调试： 系统要求](aspnet-debugging-system-requirements.md)   
[如何： 运行辅助进程的用户帐户](how-to-run-the-worker-process-under-a-user-account.md)   
[如何： 查找 ASP.NET 进程的名称](how-to-find-the-name-of-the-aspnet-process.md)   
[调试已部署的 Web 应用程序](debugging-deployed-web-applications.md)   
[演练： 调试 Web 窗体](walkthrough-debugging-a-web-form.md)   
[如何： 调试 ASP.NET 异常](how-to-debug-aspnet-exceptions.md)   
[调试 Web 应用程序：错误和疑难解答](debugging-web-applications-errors-and-troubleshooting.md)
  
