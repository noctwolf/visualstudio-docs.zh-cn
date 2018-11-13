---
title: 构建的 Azure 命令行 |Microsoft Docs
description: 构建的 Azure 命令行
author: ghogen
manager: douge
assetId: 94b35d0d-0d35-48b6-b48b-3641377867fd
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/05/2017
ms.author: ghogen
ms.openlocfilehash: fce752d91ebaa765e18efef117a3b6efe750119c
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001568"
---
# <a name="building-azure-projects-from-the-command-line"></a>生成命令行中的 Azure 项目
使用 Microsoft 生成引擎 (MSBuild)，可以生成在未安装 Visual Studio 的生成实验室环境中的产品。 MSBuild 对可扩展且 Microsoft 完全支持的项目文件使用 XML 格式。 使用 MSBuild 文件格式，您可以描述的项目必须是针对一个或多个平台和配置。

此外可以在命令行中，运行 MSBuild，本主题介绍了该方法。 通过在命令行上设置属性，可以生成项目的特定配置。 同样，您还可以定义 MSBuild 将生成的目标。 有关命令行参数和 MSBuild 的详细信息，请参阅[MSBuild 命令行参考](https://msdn.microsoft.com/library/ms164311.aspx)。

## <a name="msbuild-parameters"></a>MSBuild 参数
若要创建包的最简单方法是运行 MSBuild 并使用`/t:Publish`选项。 默认情况下，此命令将创建与项目的根文件夹相关的目录例如`<ProjectDirectory>\bin\Configuration\app.publish\`。 生成 Azure 项目时，生成两个文件： 包文件本身和附带的配置文件：

* 包文件 (`project.cspkg`)
* 配置文件 (`ServiceConfiguration.TargetProfile.cscfg`)

默认情况下，每个 Azure 项目均包含针对本地 （调试） 生成的一个服务配置文件，另一个用于云 （过渡或生产） 生成。 但是，可以添加或删除服务配置文件，根据需要。 生成 Visual Studio 中的包时，系统会要求哪个服务配置文件与包一起包含。 使用 MSBuild 生成包时，默认情况下包含本地服务配置文件。 若要将不同的服务配置文件中，设置`TargetProfile`MSBuild 命令的属性 (`MSBuild /t:Publish /p:TargetProfile=ProfileName`)。

如果你想要存储的包和配置文件使用备用目录，通过设置路径`/p:PublishDir=Directory\`选项，包括尾随反斜杠分隔符。

## <a name="next-steps"></a>后续步骤
生成包后，可以将其部署到 Azure。