---
title: 如何： 创建本地化的引导程序包 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
helpviewer_keywords:
- localized bootstrapper packages
- dependencies, creating localized bootstrapper packages
- prerequisites, creating localized bootstrapper packages
ms.assetid: 66a1bc7e-6540-4164-963d-557196a69d8a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1083633410c42c63f8c3e9a2ff341a2278f0b63a
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2018
ms.locfileid: "39153210"
---
# <a name="how-to-create-a-localized-bootstrapper-package"></a>如何： 创建本地化的引导程序包
创建引导程序包后，可以通过创建每个区域设置的两个文件创建引导程序包的本地化的版本： 软件许可条款文件 (如*eula.rtf*) 和包清单 (*package.xml*)。  
  
 默认情况下，Visual Studio 2010 只包括 .NET Framework 4、.NET Framework 4 Client Profile、F# Runtime 2.0 和 F# Runtime 4.0 的本地化引导程序包。 你可以通过完成三步操作来为其他引导程序创建本地化包。  
  
1.  创建一个文件夹中的区域设置名称命名*\Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\\<BootstrapperPackageName >*。  
  
2.  创建包含引导程序包的软件许可条款的文件并将其放入新的文件夹中。  
  
3.  创建名为的包清单*package.xml*、 更新字符串和区域性，并将该文件放入新文件夹。 如果你已在目标语言中创建的 Visual Studio 引导程序，则可以复制 Visual Studio *package.xml*文件，并在此步骤中对其进行修改。  
  
> [!NOTE]
>  如果将安装项目来部署应用程序，可以通过更改本地化应用程序**本地化**属性。  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-localized-bootstrapper-package"></a>创建本地化的引导程序包  
  
1.  创建以区域设置名称命名的文件夹。  
  
     在 32 位计算机上创建的文件夹中*\Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\\<BootstrapperPackageName >\\* 文件夹。  
  
     在 64 位计算机上创建的文件夹中*\Program Files (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\\<BootstrapperPackageName >\\* 文件夹。  
  
     下表显示可以用来匹配区域设置的文件夹名称。  
  
    |区域设置|文件夹名称|  
    |------------|-----------------|  
    |中文(简体)|zh-Hans|  
    |中文(繁体)|zh-Hant|  
    |捷克语|cs|  
    |德语|de|  
    |英语|en|  
    |西班牙语|es|  
    |法语|fr|  
    |意大利语|it|  
    |朝鲜语|ko|  
    |日语|ja|  
    |波兰语|pl|  
    |葡萄牙语(巴西)|pt-BR|  
    |俄语|ru|  
    |土耳其语|tr|  
  
2.  创建包含引导程序包的软件许可条款的文件并将其放入新的文件夹中。  
  
3.  创建名为的包清单*package.xml*并将其放入新的文件夹。 有关详细信息，请参阅[如何： 创建程序包清单](../deployment/how-to-create-a-package-manifest.md)。  
  
4.  更新包清单的 `<Strings>` 部分，使字符串以正确的区域设置语言表示。  
  
5.  更改 `<String Name="Culture">` 值以匹配文件夹名称。  
  
6.  保存*package.xml*文件。  
  
### <a name="to-create-a-bootstrapper-package-for-net-framework-35-service-pack-1-localized-in-french"></a>为用法语本地化的 .NET Framework 3.5 Service Pack 1 创建引导程序包  
  
1.  创建名为的文件夹*fr*。 该文件夹名称必须与区域设置名称匹配。  
  
     在 32 位计算机上创建的文件夹中*\Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\\* 文件夹。  
  
     在 64 位计算机上创建的文件夹中*\Program Files (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\\* 文件夹。  
  
2.  将软件许可条款到本地化的版本放*fr*文件夹。  
  
3.  复制*\Program 文件 (x86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\en\package.xml*的文件*fr*文件夹，并打开 XML 设计器中的文件。  
  
4.  更新包清单的 `<Strings>` 部分，以便用法语表示错误字符串。  
  
5.  更改`<String Name="Culture">`值设为*fr*。  
  
6.  保存*package.xml*文件。  
  
## <a name="see-also"></a>请参阅  
 [创建引导程序包](../deployment/creating-bootstrapper-packages.md)   
 [应用程序部署必备](../deployment/application-deployment-prerequisites.md)   
 [如何：创建程序包清单](../deployment/how-to-create-a-package-manifest.md)