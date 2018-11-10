---
title: Publish-webapplicationwebsite （Windows PowerShell 脚本） |Microsoft Docs
description: 了解如何将 web 项目发布到 Azure 网站。 如果它们不存在，此脚本在 Azure 订阅中创建所需的资源。
author: ghogen
manager: douge
assetId: 63cfaa2d-f04d-40dc-8677-345385c278d5
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: 175181d5d866e9d7fab51eaf7c3262e47d0ed6a8
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001559"
---
# <a name="publish-webapplicationwebsite-windows-powershell-script"></a>Publish-WebApplicationWebSite（Windows PowerShell 脚本）
## <a name="syntax"></a>语法
将 web 项目发布到 Azure 网站。 如果它们不存在，该脚本在 Azure 订阅中创建所需的资源。

    Publish-WebApplicationWebSite
    –Configuration <configuration>
    -SubscriptionName <subscriptionName>
    -WebDeployPackage <packageName>
    -DatabaseServerPassword @{Name = "name"; Password = "password"}
    -SendHostMessagesToOutput
    -Verbose


## <a name="configuration"></a>配置
描述部署的详细信息的 JSON 配置文件的路径。

| 参数 | 默认值 |
| --- | --- |
| 别名 |无 |
| 是否必需？ |true |
| 位置 |命名的 |
| 默认值 |无 |
| 接受管道输入？ |False |
| 接受通配符？ |False |

## <a name="subscriptionname"></a>SubscriptionName
你想要在其中创建网站的 Azure 订阅的名称。

| 参数 | 默认值 |
| --- | --- |
| 别名 |无 |
| 是否必需？ |False |
| 位置 |命名的 |
| 默认值 |无 |
| 接受管道输入？ |False |
| 接受通配符？ |False |

## <a name="webdeploypackage"></a>WebDeployPackage
若要发布到网站的 web 部署包路径。 可以通过使用 Visual Studio 中的发布 Web 向导来创建此包。 有关详细信息，请参阅[开始使用 Azure 云服务和 ASP.NET](http://go.microsoft.com/fwlink/p/?LinkID=623089)。

| 参数 | 默认值 |
| --- | --- |
| 别名 |无 |
| 是否必需？ |False |
| 位置 |命名的 |
| 默认值 |无 |
| 接受管道输入？ |False |
| 接受通配符？ |False |

## <a name="databaseserverpassword"></a>DatabaseServerPassword
用户名和密码在 Azure 中的 SQL 数据库中。

| 参数 | 默认值 |
| --- | --- |
| 别名 |无 |
| 是否必需？ |False |
| 位置 |命名的 |
| 默认值 |无 |
| 接受管道输入？ |False |
| 接受通配符？ |False |

## <a name="sendhostmessagestooutput"></a>SendHostMessagesToOutput
如果为 true，打印来自脚本的消息到输出流。

| 参数 | 默认值 |
| --- | --- |
| 别名 |无 |
| 是否必需？ |False |
| 位置 |命名的 |
| 默认值 |False |
| 接受管道输入？ |False |
| 接受通配符？ |False |

## <a name="remarks"></a>备注
有关完整说明如何使用脚本创建的开发和测试环境，请参阅[使用 Windows PowerShell 脚本发布到开发和测试环境](vs-azure-tools-publishing-using-powershell-scripts.md)。

JSON 配置文件指定什么是要部署的详细信息。 它包括创建项目，如名称和用户名的网站时指定的信息。 如果有的话，它还包括配置、 数据库。 下面的代码演示一个示例 JSON 配置文件：

    {
        "environmentSettings": {
            "webSite": {
                "name": "WebApplication10554",
                "location": "West US"
            },
            "databases": [
                {
                    "connectionStringName": "DefaultConnection",
                    "databaseName": "WebApplication10554_db",
                    "serverName": "iss00brc88",
                    "user": "sqluser2",
                    "password": "",
                    "edition": "",
                    "size": "",
                    "collation": "",
                    "location": "West US"
                }
            ]
        }
    }

可以编辑 JSON 配置文件以更改部署的内容。 网站部分是必需的但数据库部分是可选的。

## <a name="next-steps"></a>后续步骤
有关详细信息，请参阅[Publish-webapplicationvm （Windows PowerShell 脚本）](vs-azure-tools-publish-webapplicationvm.md)

