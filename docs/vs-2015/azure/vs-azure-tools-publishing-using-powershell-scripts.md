---
title: 使用 Windows PowerShell 脚本发布到开发和测试环境 |Microsoft Docs
description: 了解如何使用 Visual Studio 从 Windows PowerShell 脚本发布到开发和测试环境。
author: ghogen
manager: douge
assetId: 5fff1301-5469-4d97-be88-c85c30f837c1
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: 9d0142c52fbe40256fc0ab6ec0d5d9fdade243b7
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001524"
---
# <a name="using-windows-powershell-scripts-to-publish-to-dev-and-test-environments"></a>使用 Windows PowerShell 脚本发布到开发和测试环境

在 Visual Studio 中创建 web 应用程序时，可以生成更高版本可以使用它来自动为 Azure 应用服务或虚拟机中的 Web 应用发布到 Azure 网站的 Windows PowerShell 脚本。 可以编辑和扩展以满足应用需求，在 Visual Studio 编辑器中的 Windows PowerShell 脚本或将脚本与现有构建、 测试和发布脚本相集成。

使用这些脚本，你可以设置自定义的版本 （也称为开发和测试环境） 供临时使用你的网站。 例如，您可能设置了你的网站在 Azure 虚拟机上或运行测试套件、 再现 bug、 测试 bug 修复程序、 试验建议的更改，或设置自定义环境用于演示或展示了网站上的过渡槽的特定版本。 创建用于发布你的项目的脚本后，可以通过重新运行该脚本，根据需要重新创建相同的环境或使用 web 应用程序，创建用于测试的自定义环境生成运行该脚本。

## <a name="prerequisites"></a>系统必备

* Azure SDK 2.3 或更高版本。 请参阅[Visual Studio 下载](http://go.microsoft.com/fwlink/?LinkID=624384)。 （您不需要 Azure SDK 就能生成 web 项目的脚本。 此功能适用于 web 项目，不在云服务中的 web 角色。）
* Azure PowerShell 0.7.4 或更高版本。 请参阅[如何安装和配置 Azure PowerShell](/powershell/azure/overview)。
* [Windows PowerShell 3.0](http://go.microsoft.com/?linkid=9811175)或更高版本。

## <a name="additional-tools"></a>其他工具

可使用 Visual Studio 中的 PowerShell 进行 Azure 开发的其他工具和资源。 请参阅[PowerShell Tools for Visual Studio](http://go.microsoft.com/fwlink/?LinkId=404012)。

## <a name="generating-the-publish-scripts"></a>生成发布脚本

您可以生成发布脚本时按照创建一个新的项目托管网站的虚拟机[这些说明](/azure/virtual-machines/windows/classic/web-app-visual-studio.md?toc=%2fazure%2fvirtual-machines%2fwindows%2fclassic%2ftoc.json)。 此外可以[生成 Azure 应用服务中发布的 web 应用的脚本](/azure/app-service/scripts/app-service-powershell-deploy-github)。

## <a name="scripts-that-visual-studio-generates"></a>Visual Studio 将生成的脚本

Visual Studio 将生成一个名为的解决方案级文件夹**PublishScripts** ，其中包含两个 Windows PowerShell 文件、 一个针对你的虚拟机或网站，并包含可以在中使用的函数的模块发布脚本脚本。 Visual Studio 还生成一个文件中指定要部署的项目的详细信息的 JSON 格式。

### <a name="windows-powershell-publish-script"></a>Windows PowerShell 发布脚本

发布脚本包含有关部署到网站或虚拟机的特定发布步骤。 Visual Studio 提供语法突出显示适用于 Windows PowerShell 开发。 有关这些函数可用，并且可以自由编辑脚本以适应不断变化的要求中的函数帮助。

### <a name="windows-powershell-module"></a>Windows PowerShell 模块

Visual Studio 将生成的 Windows PowerShell 模块包含发布脚本使用的函数。 这些 Azure PowerShell 函数不应修改。 请参阅[如何安装和配置 Azure PowerShell](/powershell/azure/overview)。

### <a name="json-configuration-file"></a>JSON 配置文件

在中创建 JSON 文件**配置**文件夹和包含配置数据用于确切指定哪些资源将部署到 Azure。 Visual Studio 生成的名称是文件的项目的名称-WAWS-dev.json 如果你创建网站或项目名称 VM dev.json 如果创建的虚拟机。 下面是你创建网站时，将生成的 JSON 配置文件的示例。 值的大多数都一目了然。 网站名称是由 Azure 生成，因此可能会符合您的项目名称。

```json
{
    "environmentSettings": {
        "webSite": {
            "name": "WebApplication26632",
            "location": "West US"
        },
        "databases": [{
            "connectionStringName": "DefaultConnection",
            "databaseName": "WebApplication26632_db",
            "serverName": "YourDatabaseServerName",
            "user": "sqluser2",
            "password": "",
            "edition": "",
            "size": "",
            "collation": "",
            "location": "West US"
        }]
    }
}
```

当创建虚拟机时，JSON 配置文件看起来类似于以下。 云服务创建为虚拟机的容器。 虚拟机包含通过 HTTP 和 HTTPS，web 访问的普通终结点以及用于 Web 部署，这样就可以从本地计算机、 远程桌面和 Windows PowerShell 发布到网站终结点。

```json
{
    "environmentSettings": {
        "cloudService": {
            "name": "myusernamevm1",
            "affinityGroup": "",
            "location": "West US",
            "virtualNetwork": "",
            "subnet": "",
            "availabilitySet": "",
            "virtualMachine": {
                "name": "myusernamevm1",
                "vhdImage": "a699494373c04fc0bc8f2bb1389d6106__Win2K8R2SP1-Datacenter-201403.01-en.us-127GB.vhd",
                "size": "Small",
                "user": "vmuser1",
                "password": "",
                "enableWebDeployExtension": true,
                "endpoints": [{
                        "name": "Http",
                        "protocol": "TCP",
                        "publicPort": "80",
                        "privatePort": "80"
                    },
                    {
                        "name": "Https",
                        "protocol": "TCP",
                        "publicPort": "443",
                        "privatePort": "443"
                    },
                    {
                        "name": "WebDeploy",
                        "protocol": "TCP",
                        "publicPort": "8172",
                        "privatePort": "8172"
                    },
                    {
                        "name": "Remote Desktop",
                        "protocol": "TCP",
                        "publicPort": "3389",
                        "privatePort": "3389"
                    },
                    {
                        "name": "Powershell",
                        "protocol": "TCP",
                        "publicPort": "5986",
                        "privatePort": "5986"
                    }
                ]
            }
        },
        "databases": [{
            "connectionStringName": "",
            "databaseName": "",
            "serverName": "",
            "user": "",
            "password": ""
        }],
        "webDeployParameters": {
            "iisWebApplicationName": "Default Web Site"
        }
    }
}
```

可以编辑 JSON 配置，以更改运行发布脚本时，会发生什么情况。 `cloudService`并`virtualMachine`各节是必需的但可以删除`databases`部分如果您不需要它。 在 Visual Studio 将生成的默认配置文件中为空的属性是可选的;默认配置文件中具有值的这些属性是必需的。

如果而不是在 Azure 中有单个生产站点拥有的网站具有多个部署环境 （称为槽），则可以在 JSON 配置文件中包含的网站的槽名称。 例如，如果你有一个名为的网站**mysite**和槽的名称为**测试**则 URI 为`mysite-test.cloudapp.net`，但要在配置文件中使用的正确名称为 mysite （test）。 您可以仅才这样做网站和槽已存在于你的订阅。 如果它们不存在，创建该网站由运行该脚本而不指定槽，然后创建中的槽[Azure 门户](https://portal.azure.com/)，并且以后运行该脚本使用修改后的网站名称。 有关 web 应用部署槽位的详细信息，请参阅[设置过渡环境中 Azure 应用服务 web 应用的](/azure/app-service/web-sites-staged-publishing)。

## <a name="how-to-run-the-publish-scripts"></a>如何运行发布脚本

如果您从未运行 Windows PowerShell 脚本之前，必须首先设置执行策略以使脚本能够运行。 策略是一项安全功能来防止用户运行 Windows PowerShell 脚本，如果它们免受恶意软件或病毒涉及执行脚本。

### <a name="run-the-script"></a>运行脚本

1. 创建你的项目的 Web 部署包。 Web 部署包是包含你想要将复制到你的网站或虚拟机的文件的压缩的存档 （.zip 文件）。 对于任何 web 应用程序，可以在 Visual Studio 中创建 Web 部署包。

   ![创建 Web 部署包](./media/vs-azure-tools-publishing-using-powershell-scripts/IC767885.png)

   有关详细信息，请参阅[如何： 在 Visual Studio 中创建 Web 部署包](https://msdn.microsoft.com/library/dd465323.aspx)。 此外可以自动创建 Web 部署包，如中所述[自定义和扩展发布脚本](#customizing-and-extending-publish-scripts)。

1. 在中**解决方案资源管理器**，打开该脚本的上下文菜单，然后选择**使用 PowerShell ISE 打开**。
1. 如果第一次在此计算机上运行 Windows PowerShell 脚本，使用管理员特权打开命令提示符窗口并键入以下命令：

    ```powershell
    Set-ExecutionPolicy RemoteSigned
    ```

1. 使用以下命令登录到 Azure。

    ```powershell
    Add-AzureAccount
    ```

    出现提示时，提供用户名和密码。

    请注意，当自动编写脚本，提供 Azure 凭据的此方法不起作用。 相反，应使用`.publishsettings`文件来提供凭据。 一次只使用该命令**Get-azurepublishsettingsfile**从 Azure 下载文件和此后**Import-azurepublishsettingsfile**导入文件。 有关详细说明，请参阅[如何安装和配置 Azure PowerShell](/powershell/azure/overview)。

1. （可选）如果你想要创建虚拟机等 Azure 资源，数据库和网站而不发布 web 应用程序，使用**Publish-WebApplication.ps1**命令与 **-配置**参数设置为 JSON 配置文件。 此命令行使用 JSON 配置文件来确定要创建的资源。 因为它对其他命令行参数使用默认设置，它会创建资源，但不发布 web 应用程序。 -Verbose 选项可提供有关发生了什么情况的详细信息。

    ```powershell
    Publish-WebApplication.ps1 -Verbose –Configuration C:\Path\WebProject-WAWS-dev.json
    ```

1. 使用**Publish-WebApplication.ps1**命令，来调用脚本并发布 web 应用程序的以下示例之一所示。 如果你需要重写默认设置为任何其他参数，例如订阅名称、 发布包名称、 虚拟机凭据或数据库服务器凭据，可以指定这些参数。 使用 **– Verbose**选项以查看发布过程的进度有关的详细信息。

    ```powershell
    Publish-WebApplication.ps1 –Configuration C:\Path\WebProject-WAWS-dev-json `
    –SubscriptionName Contoso `
    -WebDeployPackage C:\Documents\Azure\ADWebApp.zip `
    -DatabaseServerPassword @{Name="dbServerName";Password="adminPassword"} `
    -Verbose
    ```

    如果要创建虚拟机，该命令看起来如下所示。 此示例还演示如何指定多个数据库的凭据。 这些脚本创建的虚拟机，SSL 证书不受信任的根颁发机构颁发。 因此，您需要使用 **– AllowUntrusted**选项。

    ```powershell
    Publish-WebApplication.ps1 `
    -Configuration C:\Path\ADVM-VM-test.json `
    -SubscriptionName Contoso `
    -WebDeployPackage C:\Path\ADVM.zip `
    -AllowUntrusted `
    -VMPassword @{name = "vmUserName"; password = "YourPasswordHere"} `
    -DatabaseServerPassword @{Name="server1";Password="adminPassword1"}, @{Name="server2";Password="adminPassword2"} `
    -Verbose
    ```

    该脚本可以创建数据库，但不会创建数据库服务器。 如果你想要创建数据库服务器，则可以使用**New-azuresqldatabaseserver** Azure 模块中的函数。

## <a name="customizing-and-extending-the-publish-scripts"></a>自定义和扩展发布脚本

您可以自定义发布脚本和 JSON 配置文件。 Windows PowerShell 模块中的函数**AzureWebAppPublishModule.psm1**不应修改。 如果只是想要指定不同的数据库或更改某些虚拟机的属性，编辑 JSON 配置文件。 如果你想要扩展脚本以自动生成和测试你的项目的功能，可以实现函数存根中的**Publish-WebApplication.ps1**。

若要自动生成项目，添加代码调用到 MSBuild`New-WebDeployPackage`中此代码示例所示。 MSBuild 命令的路径是已安装的 Visual Studio 的版本而异。 若要获取正确的路径，可以使用函数**Get-msbuildcmd**，在此示例中所示。

### <a name="to-automate-building-your-project"></a>若要自动生成你的项目

1. 添加`$ProjectFile`global param 节中的参数。

    ```powershell
    [Parameter(Mandatory = $false)]
    [ValidateScript({Test-Path $_ -PathType Leaf})]
    [String]
    $ProjectFile,
    ```

1. 将函数复制`Get-MSBuildCmd`到脚本文件。

    ```powershell
    function Get-MSBuildCmd
    {
            process
    {

                $path =  Get-ChildItem "HKLM:\SOFTWARE\Microsoft\MSBuild\ToolsVersions\" |
                                    Sort-Object {[double]$_.PSChildName} -Descending |
                                    Select-Object -First 1 |
                                    Get-ItemProperty -Name MSBuildToolsPath |
                                    Select -ExpandProperty MSBuildToolsPath

                $path = (Join-Path -Path $path -ChildPath 'msbuild.exe')

            return Get-Item $path
        }
    }
    ```

1. 替换`New-WebDeployPackage`使用以下代码，并在行构造的占位符替换为`$msbuildCmd`。 此代码适用于 Visual Studio 2015。 如果使用 Visual Studio 2017，更改**VisualStudioVersion**属性设置为`15.0`(`12.0`适用于 Visual Studio 2013)。

    ```powershell
    function New-WebDeployPackage
    {
        #Write a function to build and package your web application
    ```

    若要生成 web 应用程序，请使用 MsBuild.exe。 有关帮助，请参阅 MSBuild 命令行参考： [http://go.microsoft.com/fwlink/?LinkId=391339](http://go.microsoft.com/fwlink/?LinkId=391339)

    ```powershell
    Write-VerboseWithTime 'Build-WebDeployPackage: Start'

    $msbuildCmd = '"{0}" "{1}" /T:Rebuild;Package /P:VisualStudioVersion=14.0 /p:OutputPath="{2}\MSBuildOutputPath" /flp:logfile=msbuild.log,v=d' -f (Get-MSBuildCmd), $ProjectFile, $scriptDirectory

    Write-VerboseWithTime ('Build-WebDeployPackage: ' + $msbuildCmd)
    ```

### <a name="start-execution-of-the-build-command"></a>启动生成命令的执行

```powershell
$job = Start-Process cmd.exe -ArgumentList('/C "' + $msbuildCmd + '"') -WindowStyle Normal -Wait -PassThru

if ($job.ExitCode -ne 0) {
    throw('MsBuild exited with an error. ExitCode:' + $job.ExitCode)
}

#Obtain the project name
$projectName = (Get-Item $ProjectFile).BaseName

#Construct the path to web deploy zip package
$DeployPackageDir =  '.\MSBuildOutputPath\_PublishedWebsites\{0}_Package\{0}.zip' -f $projectName

#Get the full path for the web deploy zip package. This is required for MSDeploy to work
$WebDeployPackage = Resolve-Path –LiteralPath $DeployPackageDir

Write-VerboseWithTime 'Build-WebDeployPackage: End'

return $WebDeployPackage
}
```

1. 调用`New-WebDeployPackage`此行之前的函数：`$Config = Read-ConfigFile $Configuration`适用于 web 应用或`$Config = Read-ConfigFile $Configuration -HasWebDeployPackage:([Bool]$WebDeployPackage)`的虚拟机。

    ```powershell
    if($ProjectFile)
    {
    $WebDeployPackage = New-WebDeployPackage
    }
    ```

1. 调用自定义的脚本从命令行通过传递`$Project`参数，如以下示例所示：

    ```powershell
    .\Publish-WebApplicationVM.ps1 -Configuration .\Configurations\WebApplication5-VM-dev.json `
    -ProjectFile ..\WebApplication5\WebApplication5.csproj `
    -VMPassword @{Name="VMUser";Password="Test.123"} `
    -AllowUntrusted `
    -Verbose
    ```

    若要自动执行测试的应用程序，将代码添加到`Test-WebApplication`。 请务必取消注释中的行**Publish-WebApplication.ps1**调用这些函数。 如果不提供实现，你可以手动生成使用 Visual Studio 项目，然后运行发布脚本发布到 Azure。

## <a name="publishing-function-summary"></a>发布函数摘要
若要获取可以在 Windows PowerShell 命令提示符下使用的函数的帮助，请使用命令`Get-Help function-name`。 帮助中包含参数帮助和示例。 在脚本源文件中也是相同的帮助文本**AzureWebAppPublishModule.psm1**并**Publish-WebApplication.ps1**。 在 Visual Studio 语言本地化的脚本和帮助。

**AzureWebAppPublishModule**

| 功能名称 | 描述 |
| --- | --- |
| 添加 AzureSQLDatabase |创建新的 Azure SQL 数据库。 |
| Add-azuresqldatabases |从 Visual Studio 将生成的 JSON 配置文件中的值创建 Azure SQL 数据库。 |
| 添加 AzureVM |创建 Azure 虚拟机并返回已部署的 VM 的 URL。 该函数将设置先决条件，然后调用**New-azurevm**函数 （Azure 模块） 来创建新的虚拟机。 |
| Add-azurevmendpoints |将新的输入终结点添加到虚拟机并返回包含新的终结点的虚拟机。 |
| Add-azurevmstorage |当前订阅中创建新的 Azure 存储帐户。 "Devtest"后面是一个唯一的字母数字字符串开头开始的帐户的名称。 该函数返回新的存储帐户的名称。 指定一个位置或地缘组的新的存储帐户。 |
| 添加 AzureWebsite |使用指定的名称和位置创建一个网站。 此函数将调用**New-azurewebsite** Azure 模块中的函数。 如果订阅不包含具有指定名称的网站，此函数将创建该网站，并返回一个网站对象。 否则，它将返回 `$null`。 |
| 备份订阅 |保存当前 Azure 订阅中的`$Script:originalSubscription`变量在脚本范围中。 此函数将保存当前 Azure 订阅 (通过`Get-AzureSubscription -Current`) 及其存储帐户，以及此脚本更改的订阅 (存储在变量`$UserSpecifiedSubscription`) 及其存储帐户，在脚本范围中。 保存这些值，您可以使用一个函数，如`Restore-Subscription`，以原始的当前订阅和存储帐户还原到当前状态，如果当前状态发生更改。 |
| 查找 AzureVM |获取指定的 Azure 虚拟机。 |
| Format-devtestmessagewithtime |预先计算的日期和时间的消息。 此函数用于为错误和详细流写入消息。 |
| Get AzureSQLDatabaseConnectionString |汇编一个连接字符串以连接到 Azure SQL 数据库。 |
| Get-azurevmstorage |返回的名称模式的第一个存储帐户名称"开发测试 *"（不区分大小写） 中指定的位置或地缘组。如果"devtest*"存储帐户的位置或地缘组与不匹配，此函数将忽略它。 指定一个位置或地缘组。 |
| Get-msdeploycmd |返回运行 MsDeploy.exe 工具的命令。 |
| New-azurevmenvironment |查找或与 JSON 配置文件中的值匹配的订阅中创建虚拟机。 |
| Publish-webpackage |使用 MsDeploy.exe 和 web 发布包。若要将资源部署到网站的 zip 文件。 此函数不生成任何输出。 如果调用 MSDeploy.exe 失败，该函数将引发异常。 若要获取更详细的输出，请使用 **-Verbose**选项。 |
| Publish-webpackagetovm |验证参数值，然后调用**Publish-webpackage**函数。 |
| 阅读-ConfigFile |验证 JSON 配置文件并返回所选值的哈希表。 |
| 还原订阅 |将当前订阅重置为原始订阅。 |
| Test-azuremodule |返回`$true`如果安装的 Azure 模块版本为 0.7.4 或更高版本。 返回`$false`如果模块未安装或更低的版本。 此函数没有任何参数。 |
| 测试 AzureModuleVersion |返回`$true`如果 Azure 模块的版本为 0.7.4 或更高版本。 返回`$false`如果模块未安装或更低的版本。 此函数没有任何参数。 |
| 测试 HttpsUrl |将输入的 URL 转换为 System.Uri 对象。 返回`$True`如果 URL 是绝对的并且其方案为 https。 返回`$false`如果 URL 是相对、 其方案不是 HTTPS，或输入的字符串不能转换为 URL。 |
| 测试成员 |返回`$true`如果属性或方法是对象的成员。 否则返回 `$false`。 |
| 写入 ErrorWithTime |写入以当前时间作为前缀的错误消息。 此函数将调用**Format-devtestmessagewithtime**函数来添加消息写入错误流之前的时间。 |
| 写入 HostWithTime |将消息写入主机程序 (**Write-host**) 以当前时间作为前缀。 写入主机程序的效果各不相同。 大多数程序中承载 Windows PowerShell 将这些消息写入到标准输出。 |
| 写入 VerboseWithTime |写入以当前时间作为前缀的详细消息。 因为它调用**Write-verbose**，仅当使用运行该脚本所显示的消息**Verbose**参数，或者当**VerbosePreference**首选项设置为**继续**。 |

**发布 web 应用程序**

| 功能名称 | 描述 |
| --- | --- |
| 新 AzureWebApplicationEnvironment |创建 Azure 资源，例如网站或虚拟机。 |
| 新 WebDeployPackage |未实现此函数。 你可以在此函数来构建你的项目中添加命令。 |
| 发布 AzureWebApplication |将发布到 Azure 的 web 应用程序。 |
| 发布 web 应用程序 |创建和部署 Web 应用、 虚拟机、 SQL 数据库和 Visual Studio web 项目的存储帐户。 |
| 测试 web 应用程序 |未实现此函数。 在此函数可测试应用程序中，可以添加命令。 |

## <a name="next-steps"></a>后续步骤
了解 PowerShell 脚本通过读取[使用 Windows PowerShell 编写脚本](https://technet.microsoft.com/library/bb978526.aspx)，并查看其他 Azure PowerShell 脚本在[脚本中心](https://azure.microsoft.com/documentation/scripts/)。
