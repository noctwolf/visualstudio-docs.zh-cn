---
title: 如何： 指定 Visual Studio 复制文件的位置 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, specifying location
- Publish Location property
ms.assetid: 6c552700-dda3-49fe-af98-4717344fda07
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b2a4d642bc551127f34fe7a64ec01665b7ace70
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "39078623"
---
# <a name="how-to-specify-where-visual-studio-copies-the-files"></a>如何： 指定 Visual Studio 复制文件的位置
使用 ClickOnce 发布应用程序时，“`Publish Location`”属性指定放置应用程序文件和清单的位置。 这可以是文件路径或 FTP 服务器的路径。  
  
 您可以指定`Publish Location`上的属性**发布**页**项目设计器**，或使用发布向导。 有关详细信息，请参阅[如何： 发布 ClickOnce 应用程序使用发布向导](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)。  
  
> [!NOTE]
>  当使用 ClickOnce 安装多个版本的应用程序时，安装会将应用程序的早期版本移动到位于你指定的发布位置的名为“Archive”的文件夹中。 按照这种方式对早期版本进行存档，可以使安装目录与早期版本所在的文件夹分开。  
  
### <a name="to-specify-a-publishing-location"></a>指定发布位置  
  
1.  在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。  
  
2.  单击**发布**选项卡。  
  
3.  在中**发布位置**字段中，使用以下格式之一输入发布位置：  
  
    -   若要发布到文件共享或磁盘路径，通过使用 UNC 路径，或者输入的路径 (*\\\Server\ApplicationName*) 或文件路径 (*C:\Deploy\ApplicationName*)。  
  
    -   若要将发布到 FTP 服务器，输入在路径中使用格式*ftp://ftp.microsoft.com/\<应用程序名称 >*。  
  
     请注意，文本必须位于**发布位置**框中使浏览 (**...**) 按钮正常工作。  
  
## <a name="see-also"></a>请参阅  
 [发布 ClickOnce 应用程序](../deployment/publishing-clickonce-applications.md)   
 [如何： 发布 ClickOnce 应用程序使用发布向导](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)