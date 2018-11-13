---
title: Publish-webapplicationvm |Microsoft Docs
description: 了解如何部署到虚拟机的 web 应用程序。 如果它们不存在，此脚本在 Azure 订阅中创建所需的资源。
author: ghogen
manager: douge
assetId: de4cec95-f73f-44d9-babd-9f47f2633cdb
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: c2383e6d7b14d801a391a725f0482736fb926cd1
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001581"
---
# <a name="publish-webapplicationvm-windows-powershell-script"></a>Publish-WebApplicationVM（Windows PowerShell 脚本）
将部署到虚拟机的 web 应用程序。 如果它们不存在，该脚本在 Azure 订阅中创建所需的资源。

```
Publish-WebApplicationVM
–Configuration <configuration>
-SubscriptionName <subscriptionName>
-WebDeployPackage <packageName>
-VMPassword @{Name = "name"; Password = "password")
-DatabaseServerPassword @{Name = "name"; Password = "password"}
-SendHostMessagesToOutput
-Verbose
```

### <a name="configuration"></a>配置
描述部署的详细信息的 JSON 配置文件的路径。

| 别名 | 无 |
| --- | --- |
| 是否必需？ |true |
| 位置 |命名的 |
| 默认值 |无 |
| 接受管道输入？ |False |
| 接受通配符？ |False |

### <a name="subscriptionname"></a>SubscriptionName
要在其中创建虚拟机的 Azure 订阅的名称。

| 别名 | 无 |
| --- | --- |
| 是否必需？ |False |
| 位置 |命名的 |
| 默认值 |使用订阅文件中的第一个订阅 |
| 接受管道输入？ |False |
| 接受通配符？ |False |

### <a name="webdeploypackage"></a>WebDeployPackage
若要发布到虚拟机的 web 部署包路径。 可以通过使用 Visual Studio 中的发布 Web 向导来创建此包。 请参阅[如何： 在 Visual Studio 中创建 Web 部署包](https://msdn.microsoft.com/library/dd465323.aspx)。

| 别名 | 无 |
| --- | --- |
| 是否必需？ |False |
| 位置 |命名的 |
| 默认值 |无 |
| 接受管道输入？ |False |
| 接受通配符？ |False |

### <a name="allowuntrusted"></a>AllowUntrusted
如果为 true，则允许使用的不受信任的根颁发机构签名的证书。

| 别名 | 无 |
| --- | --- |
| 是否必需？ |False |
| 位置 |命名的 |
| 默认值 |False |
| 接受管道输入？ |False |
| 接受通配符？ |False |

### <a name="vmpassword"></a>VMPassword
虚拟机帐户的凭据。 示例:-VMPassword @{名称 ="admin";密码 ="password"}

| 别名 | 无 |
| --- | --- |
| 是否必需？ |False |
| 位置 |命名的 |
| 默认值 |无 |
| 接受管道输入？ |False |
| 接受通配符？ |False |

### <a name="databaseserverpassword"></a>DatabaseServerPassword
在 Azure 中的 SQL 数据库凭据。 示例:-DatabaseServerPassword @{名称 ="admin";密码 ="password"}

| 别名 | 无 |
| --- | --- |
| 是否必需？ |False |
| 位置 |命名的 |
| 默认值 |无 |
| 接受管道输入？ |False |
| 接受通配符？ |False |

### <a name="sendhostmessagestooutput"></a>SendHostMessagesToOutput
如果为 true，打印来自脚本的消息到输出流。

| 别名 | 无 |
| --- | --- |
| 是否必需？ |False |
| 位置 |命名的 |
| 默认值 |False |
| 接受管道输入？ |False |
| 接受通配符？ |False |

## <a name="remarks"></a>备注
有关完整说明如何使用脚本创建的开发和测试环境，请参阅[使用 Windows PowerShell 脚本发布到开发和测试环境](vs-azure-tools-publishing-using-powershell-scripts.md)。

JSON 配置文件指定什么是要部署的详细信息。 它包括创建项目，例如名称、 地缘组、 VHD 映像和虚拟机的大小时指定的信息。 它还包括虚拟机，要预配的数据库上的终结点，如果有，和 web 部署参数。 下面的代码演示一个示例 JSON 配置文件：

```
{
    "environmentSettings": {
        "cloudService": {
            "name": "myvmname",
            "affinityGroup": "",
            "location": "West US",
            "virtualNetwork": "",
            "subnet": "",
            "availabilitySet": "",
            "virtualMachine": {
                "name": "myvmname",
                "vhdImage": "a699494373c04fc0bc8f2bb1389d6106__Windows-Server-2012-R2-201404.01-en.us-127GB.vhd",
                "size": "Small",
                "user": "vmuser1",
                "password": "",
                "enableWebDeployExtension": true,
                "endpoints": [
                    {
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
        "databases": [
            {
                "connectionStringName": "",
                "databaseName": "",
                "serverName": "",
                "user": "",
                "password": ""
            }
        ],
        "webDeployParameters": {
            "iisWebApplicationName": "Default Web Site"
        }
    }
}
```

可以编辑 JSON 配置文件以更改预配的内容。 虚拟机和云服务是必需的但数据库部分是可选的。

