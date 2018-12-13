---
title: 在 Visual Studio 中使用连接服务添加 Azure 存储 |Microsoft Docs
description: 使用 Visual Studio 将添加连接服务对话框中将 Azure 存储添加到您的应用程序
author: ghogen
manager: douge
assetId: 521ec044-ad4b-4828-8864-01decde2e758
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/26/2017
ms.author: ghogen
ms.openlocfilehash: 63b796d9c514602a40f15b5725c07b1b89787df1
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001267"
---
# <a name="adding-azure-storage-by-using-visual-studio-connected-services"></a>使用 Visual Studio 连接服务添加 Azure 存储
使用 Visual Studio 中，你可以以下任何使用连接到 Azure 存储**添加连接服务**对话框：

- C#云服务
- .NET 后端移动服务
- ASP.NET 网站或服务
- ASP.NET Core 服务
- Azure WebJob 服务 

连接的服务功能将所有需要的引用和连接代码添加到你的项目，并相应地修改配置文件。 

完成后，**添加连接服务**对话框自动显示文档详细介绍开始使用 blob 存储、 队列所需的步骤和表。

## <a name="connect-to-azure-storage-using-the-connected-services-dialog"></a>连接到 Azure 存储中使用连接服务对话框
1. 在 Visual Studio 中打开你的项目

1. 在中**解决方案资源管理器**，右键单击**连接的服务**节点，然后从上下文菜单，然后选择**添加连接的服务**。
   
    ![添加 Azure 连接服务](./media/vs-azure-tools-connected-services-storage/IC796702.png)

1. 在中**连接的服务**页上，选择**使用 Azure 存储的云存储**。
   
    ![添加 Azure 存储](./media/vs-azure-tools-connected-services-storage/add-azure-storage.png)

1. 在中**Azure 存储**对话框中，选择一个现有的存储帐户，并选择**添加**。
   
    如果需要创建存储帐户，请转到下一步。 否则，请跳到步骤 6。
    
    ![将现有的存储帐户添加到项目](./media/vs-azure-tools-connected-services-storage/select-azure-storage-account.png)

1. 若要创建存储帐户： 
   
   1. 选择**创建新的存储帐户**在对话框的底部。

   1. 填写**创建存储帐户**对话框中，然后选择**创建**。
      
       ![新的 Azure 存储帐户](./media/vs-azure-tools-connected-services-storage/create-storage-account.png)
      
   1. 当**Azure 存储**显示对话框，新的存储帐户会显示在列表中。 在列表中，选择新的存储帐户，然后选择**添加**。

1. 存储连接的服务将显示下**服务引用**在项目节点。
   
## <a name="how-your-project-is-modified"></a>如何修改你的项目
当完成该对话框时，Visual Studio 添加引用，并修改特定配置文件。 特定更改取决于项目类型： 

- ASP.NET 项目-[完成的操作 – ASP.NET 项目](http://go.microsoft.com/fwlink/p/?LinkId=513126)
- ASP.NET Core 项目-[完成的操作 – ASP.NET 5 项目](http://go.microsoft.com/fwlink/p/?LinkId=513124) 
- 云服务项目 （web 角色和辅助角色）-[完成的操作 – 云服务项目](http://go.microsoft.com/fwlink/p/?LinkId=516965)
- Web 作业项目-[完成的操作 – WebJob 项目](/azure/visual-studio/vs-storage-webjobs-what-happened)

## <a name="next-steps"></a>后续步骤
- [MSDN 论坛： Azure 存储](https://social.msdn.microsoft.com/forums/azure/home?forum=windowsazuredata)
- [Microsoft Azure 存储团队博客](http://blogs.msdn.com/b/windowsazurestorage/)
- [Azure 存储文档](https://docs.microsoft.com/azure/storage/)
