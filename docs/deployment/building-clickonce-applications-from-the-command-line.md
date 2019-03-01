---
title: 生成 ClickOnce 应用程序从命令行 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, from command line
- publishing
- publishing, ClickOnce
ms.assetid: d9bc6212-c584-4f72-88c9-9a4b998c555e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5576a6d219a27ad51c096ee3ddb177b656b0552e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56636952"
---
# <a name="build-clickonce-applications-from-the-command-line"></a>从命令行生成 ClickOnce 应用程序
在[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]，可以生成命令行中的项目，即使它们在集成的开发环境 (IDE) 中创建。 事实上，您可以重新生成与创建的项目[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]仅有的另一台计算机上[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]安装。 这允许你在重现生成使用自动化的过程，例如，在中心生成实验室或使用高级脚本编写技术生成项目本身的范围之外。

## <a name="use-msbuild-to-reproduce-clickonce-application-deployments"></a>使用 MSBuild 来重现 ClickOnce 应用程序部署
 当您调用 msbuild /target:publish 在命令行时，它指示 MSBuild 系统生成项目，并创建[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序 publish 文件夹中。 这相当于选择**发布**命令在 IDE 中。

 此命令执行*msbuild.exe*，这是在 Visual Studio 命令提示符环境的路径上。

 "目标"是一个指示符，MSBuild 如何处理命令。 主要目标是"生成"目标和"发布"目标。 生成目标相当于选择生成命令 （或按 f5 键） 在 IDE 中。 如果只想要生成你的项目，可以实现此目的通过键入`msbuild`。 此命令有效，因为生成目标是生成的所有项目的默认目标[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]。 这意味着您不显式需要指定 build 目标。 因此，键入`msbuild`是相同的操作键入`msbuild /target:build`。

 `/target:publish`命令告知 MSBuild 调用发布目标。 发布目标取决于生成目标。 这意味着发布操作是生成操作的超集。 例如，如果对一个 Visual Basic 进行了更改或C#自动将由发布操作重新生成源文件，相应的程序集。

 有关生成完整的信息[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]使用 Mage.exe 命令行工具创建的部署你[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]清单，请参阅[演练： 手动部署 ClickOnce 应用程序](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)。

## <a name="create-and-build-a-basic-clickonce-application-with-msbuild"></a>创建和生成基本 ClickOnce 应用程序使用 MSBuild

#### <a name="to-create-and-publish-a-clickonce-project"></a>若要创建和发布一个 ClickOnce 项目

1. 单击**新的项目**从**文件**菜单。 此时将出现“新建项目”对话框。

2. 选择**Windows 应用程序**并将其命名`CmdLineDemo`。

3. 从**构建**菜单上，单击**发布**命令。

    此步骤可确保该项目是否已正确配置以生成[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序部署。

    出现“发布向导”。

4. 在发布向导中，单击**完成**。

    Visual Studio 生成并显示名为的默认 Web 页*Publish.htm*。

5. 保存你的项目，并记下在其中存储的文件夹位置。

   上述步骤创建[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]首次发布的项目。 现在可以再现在 IDE 之外生成。

#### <a name="to-reproduce-the-build-from-the-command-line"></a>若要从命令行生成重现

1. 退出 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]。

2. 从 Windows**启动**菜单上，单击**所有程序**，然后**Microsoft Visual Studio**，然后**Visual Studio Tools**，则**Visual Studio 命令提示符**。 此时会在当前用户的根文件夹中打开命令提示符。

3. 在中**Visual Studio 命令提示符**，将当前目录更改为只生成上面的项目的位置。 例如，键入 `chdir My Documents\Visual Studio\Projects\CmdLineDemo`。

4. 若要删除现有文件中生成"以创建和发布[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]项目中，"类型`rmdir /s publish`。

    此步骤是可选的但它可确保，新文件所有由生成命令行生成。

5. 键入 `msbuild /target:publish`。

   上述步骤将生成完整[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]的子文件夹中的名为的项目的应用程序部署**发布**。 *CmdLineDemo.application*是[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]部署清单。 文件夹*CmdLineDemo_1.0.0.0*包含的文件*CmdLineDemo.exe*并*CmdLineDemo.exe.manifest*，则[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序清单。 *Setup.exe*是引导程序、 其默认配置安装[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]。 DotNetFX 文件夹中包含的可再发行组件[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]。 这是在 Web 上或者通过 UNC 或 CD/DVD 部署你的应用程序所需的文件的整个集。

## <a name="publish-properties"></a>发布属性
 在上面的过程中发布应用程序，以下属性是通过发布向导插入到项目文件。 这些属性直接影响如何[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]生成应用程序。

 在中*CmdLineDemo.vbproj* / *CmdLineDemo.csproj*:

```xml
<AssemblyOriginatorKeyFile>WindowsApplication3.snk</AssemblyOriginatorKeyFile>
<GenerateManifests>true</GenerateManifests>
<TargetZone>LocalIntranet</TargetZone>
<PublisherName>Microsoft</PublisherName>
<ProductName>CmdLineDemo</ProductName>
<PublishUrl>http://localhost/CmdLineDemo</PublishUrl>
<Install>true</Install>
<ApplicationVersion>1.0.0.*</ApplicationVersion>
<ApplicationRevision>1</ApplicationRevision>
<UpdateEnabled>true</UpdateEnabled>
<UpdateRequired>false</UpdateRequired>
<UpdateMode>Foreground</UpdateMode>
<UpdateInterval>7</UpdateInterval>
<UpdateIntervalUnits>Days</UpdateIntervalUnits>
<UpdateUrlEnabled>false</UpdateUrlEnabled>
<IsWebBootstrapper>true</IsWebBootstrapper>
<BootstrapperEnabled>true</BootstrapperEnabled>
```

 您可以覆盖这些属性在命令行而无需更改项目文件本身。 例如，将生成以下[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]而无需引导程序的应用程序部署：

```cmd
msbuild /target:publish /property:BootstrapperEnabled=false
```

 发布属性控制在[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]从**发布**，**安全**，并且**签名**的属性页**项目设计器**. 下面是发布属性以及指示每个应用程序设计器的各种属性页中的设置方式的说明：

- `AssemblyOriginatorKeyFile` 确定用于签名的密钥文件在[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序清单。 此密钥也可能用于你的程序集分配强名称。 设置此属性**签名**页**项目设计器**。

  以下属性在设置**安全**页：

- **启用 ClickOnce 安全设置**确定是否[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]在生成清单。 最初创建项目，[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]清单生成默认情况下处于关闭状态。 向导将自动打开上首次发布时此标志。

- **TargetZone**确定要发出到信任级别将[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序清单。 可能的值为"Internet"、"LocalIntranet"和"自定义"。 Internet 和 LocalIntranet 将导致一个默认权限集来发出到你[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序清单。 LocalIntranet 是默认值，并基本上是说完全信任。 自定义指定的并且只有在基类中显式指定的权限*app.manifest*文件都要发出到[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序清单。 *App.manifest*文件是完整的清单文件包含只需信任信息定义。 它是隐藏的文件，在上配置权限时，自动添加到你的项目**安全**页。

  以下属性在设置**发布**页：

- `PublishUrl` 是，应用程序将发布到在 IDE 中的位置。 插入到[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序清单，如果既没有`InstallUrl`或`UpdateUrl`指定属性。

- `ApplicationVersion` 指定的版本[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序。 这是四位数字的版本号。 如果最后一位数将"*"，则`ApplicationRevision`替换为在生成时插入到程序集清单的值。

- `ApplicationRevision` 指定的修订。 这是一个整数，它会发布在 IDE 中的每次递增。 请注意，不自动递增的生成在命令行执行。

- `Install` 确定应用程序是否已安装应用程序或运行从 Web 应用程序。

- `InstallUrl` （未显示） 是用户将在其中安装的应用程序的位置。 如果指定，此值根深蒂固*setup.exe*引导程序如果`IsWebBootstrapper`启用属性。 它也会插入到应用程序清单如果`UpdateUrl`未指定。

- `SupportUrl` （未显示） 位置中的链接**添加/删除程序**已安装应用程序对话框。

  设置以下属性**应用程序更新**对话框中，从访问**发布**页。

- `UpdateEnabled` 指示应用程序是否应检查更新。

- `UpdateMode` 指定更新前台或后台更新。

- `UpdateInterval` 指定应用程序检查更新的频率。

- `UpdateIntervalUnits` 指定是否`UpdateInterval`值为小时、 天或周为单位。

- `UpdateUrl` （未显示） 是应用程序将从其接收更新的位置。 如果指定，此值将插入到应用程序清单。

- 设置以下属性**发布选项**对话框中，从访问**发布**页。

- `PublisherName` 指定发布服务器上安装或运行该应用程序时显示的提示中显示的名称。 对于已安装的应用程序，它还用于在指定文件夹名称**启动**菜单。

- `ProductName` 指定在安装或运行应用程序时显示的提示中显示的产品的名称。 对于已安装的应用程序，它还用于在指定的快捷方式名称**启动**菜单。

- 设置以下属性**先决条件**对话框中，从访问**发布**页。

- `BootstrapperEnabled` 确定是否生成*setup.exe*引导程序。

- `IsWebBootstrapper` 确定是否*setup.exe*引导程序可通过 Web 或基于磁盘的模式。

## <a name="installurl-supporturl-publishurl-and-updateurl"></a>InstallURL、 SupportUrl、 PublishURL，和 UpdateURL
 下表显示了 ClickOnce 部署的四个 URL 选项。

|URL 选项|说明|
|----------------|-----------------|
|`PublishURL`|所需发布 ClickOnce 应用程序到 Web 站点。|
|`InstallURL`|可选。 设置此 URL 选项，则不同于安装站点时`PublishURL`。 例如，可以设置`PublishURL`到一个 FTP 路径和一组`InstallURL`为 Web URL。|
|`SupportURL`|可选。 如果不同于支持站点，则设置此 URL 选项`PublishURL`。 例如，可以设置`SupportURL`到公司的客户支持网站。|
|`UpdateURL`|可选。 设置此 URL 选项，则更新位置不同于时`InstallURL`。 例如，可以设置`PublishURL`到一个 FTP 路径和一组`UpdateURL`为 Web URL。|

## <a name="see-also"></a>请参阅
- <xref:Microsoft.Build.Tasks.GenerateBootstrapper>
- <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>
- <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest>
- [ClickOnce 安全和部署](../deployment/clickonce-security-and-deployment.md)
- [演练：手动部署 ClickOnce 应用程序](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)