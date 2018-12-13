---
title: 访问私有 Azure 云使用 Visual Studio |Microsoft Docs
description: 了解如何通过使用 Visual Studio 访问私有云资源。
author: ghogen
manager: douge
assetId: 9d733c8d-703b-44e7-a210-bb75874c45c8
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/13/2017
ms.author: ghogen
ms.openlocfilehash: 216b85e0ebf42b79c388ce217d548f2dce3c86b6
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001573"
---
# <a name="accessing-private-azure-clouds-with-visual-studio"></a>使用 Visual Studio 访问私有 Azure 云

默认情况下，Visual Studio 支持 Azure 云 REST 终结点。 在本文中，您将了解如何使用私有云证书访问并与 Visual Studio 中的私有云进行交互。

1. 在 Azure 门户中为私有云，下载发布设置文件，或与管理员联系以发布设置文件。 (该文件具有扩展名`.publishsettings`。)

1. 在 Visual Studio**服务器资源管理器**，右键单击**Azure**节点，然后选择**管理和筛选订阅**。

    ![管理订阅命令](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/IC790778.png)

1. 在中**管理 Microsoft Azure 订阅**对话框中，选择**证书**选项卡，然后选择**导入**。

    ![导入 Azure 证书](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/IC790779.png)

1. 在中**导入 Microsoft Azure 订阅**对话框中，选择**浏览**。

    ![浏览按钮在导入 Microsoft Azure 订阅对话框](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/browse-button.png)

1. 在中**开放**对话框中，浏览到保存发布设置文件的目录选择文件，然后选择**打开**。

    ![选择发布设置文件](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/select-publish-settings-file.png)

1. 当返回到**导入 Microsoft Azure 订阅**对话框中，选择**导入**。

    ![导入发布设置文件](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/IC790780.png)

    证书从发布设置文件导入 Visual Studio 中，并且你现在可以与私有云资源进行交互。

