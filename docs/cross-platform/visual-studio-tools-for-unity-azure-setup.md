---
title: "Visual Studio Tools for Unity Azure 演练设置 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: FFE17FC6-0B47-4A00-A125-01BD49E3873C
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: ba9de2e6af5c066e83b75576f9b104f20908aec6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="create-easy-tables"></a>创建简易表

Azure 上的移动应用已经初始化简易表，现在开始生成表来跟踪发送自 Unity 游戏的数据。

## <a name="setup-the-crash-heatmap-table"></a>设置故障热度地图表

1. 在 Azure 门户中，单击“所有资源”，然后选择在前面步骤中配置了简易表的移动应用。

  ![选择“移动应用”](media/vstu_azure-setup-table-schema-image1.png)

2. 向下滚动到“移动”标题，选择“简易表”。 应该不会再显示任何有关初始化应用的简易表的通知。  

  ![选择“简易表”](media/vstu_azure-setup-table-schema-image2.png)

3. 单击“添加”按钮。

  ![单击“添加”](media/vstu_azure-setup-table-schema-image3.png)

4. 将表命名为“**CrashInfo**”，然后单击“确定”。 将其余选项保留为默认设置。

  > [!WARNING]
  > 此名称必须与稍后在演练中创建的数据模型类名称匹配。

  ![命名并单击“确定”](media/vstu_azure-setup-table-schema-image4.png)

5. 新表创建完成时，将显示一条相应的通知。

> [!NOTE]
> 使用简易表时，实际上会在添加数据时动态创建表架构。 这意味着不必在此步骤中手动设置相应的数据列。

## <a name="setup-the-leaderboard-table"></a>设置排行榜表

1. 返回到“简易表”边栏选项卡，单击“添加”添加第二个表。

  ![添加第二个表](media/vstu_azure-setup-table-schema-image10.png)

2. 将新表命名为“**HighScoreInfo**”，并单击“确定”。 将其余选项保留为默认设置。

  > [!WARNING]
  > 此名称必须与稍后在演练中创建的数据模型类名称匹配。

  ![命名并单击“确定”](media/vstu_azure-setup-table-schema-image11.png)

3. 新表创建完成时，将显示一条相应的通知。


## <a name="next-step"></a>下一步

* [准备开发环境](visual-studio-tools-for-unity-azure-prepare.md)
