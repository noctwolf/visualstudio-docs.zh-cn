---
title: "Visual Studio Tools for Unity Azure 演练游戏 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: DA86FC7F-E456-4DFC-84BF-D780421508B9
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 204389c2341c3aa9f729b92b5f3d459e7b101d24
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="test-the-sample-game"></a>测试示例游戏

示例游戏是一个简单的赛车游戏，它记录有关玩家行为的数据并将其存储在 Azure 简易表中。 示例游戏还包括从 Azure 读取数据并为玩家进行可视化的场景。

此部分仅仅说明如何播放示例游戏，并确保它正常运行。 后续各部分会详细说明示例游戏的工作原理。

## <a name="starting-the-game"></a>启动游戏

1. 在 Unity 项目窗口中，导航到 **Assets/Azure Easy Tables sample game assets/Scenes** 目录。

2. 双击 **MenuScene** 打开它。

3. 在 Unity 游戏窗口中，单击“纵横比”下拉菜单，选择“16:9”。

  ![设置纵横比](media/vstu_azure-test-sample-game-image1.png)

4. 单击“播放”按钮以在 Unity 编辑器中运行游戏。


## <a name="complete-a-race"></a>完成竞赛

查看排行榜或热度地图之前，最好通过至少完成一次竞赛来创建一些示例数据。

1. 当游戏在 Unity 编辑器中运行时，单击“Race!” 按钮以开始新竞赛。

2. 使用 **WASD** 或**箭头键**驾驶汽车并围绕赛道顺时针跑完一圈。为进行示例演示，请务必与沿途的一些墙壁进行碰撞。 Unity 控制台中的调试输出应指示记录碰撞的时间。

  >[!NOTE]
  > 如果设法使汽车翻转并且无法继续竞赛，请单击“Restart”。 仅当完成一圈时，数据才会发送到 Azure。

  ![开始竞赛](media/vstu_azure-test-sample-game-image2.png)

3. 越过方格形终点线之后，游戏应显示“Finished”消息。 此时，撞车数据会上传到 Azure。

4. 如果你完成的圈速位列前 10 个最快圈速中，则系统会提示你为高分输入姓名。 输入你的姓名，然后单击“Submit”。

  ![开始竞赛](media/vstu_azure-test-sample-game-image3.png)

## <a name="view-the-heatmap"></a>查看热度地图

1. 在竞赛场景中单击“View Crash Heatmap”，或从主菜单中选择“Crash Heatmap”。

2. 热度地图场景会从 Azure 中的 CrashInfo 表加载数据，并在玩家与赛道墙壁碰撞的位置处显示透明红色球体。如果在重叠区域中发生多次撞车，则球体应显示得更亮。

  ![热度地图](media/vstu_azure-test-sample-game-image4.png)

## <a name="view-the-leaderboard"></a>查看排行榜

1. 在竞赛场景或主菜单中单击“Leaderboard”按钮。

2. 排行榜场景从 Azure 中的 HighScoreInfo 表加载高分数据，并为每个高分项显示玩家姓名和圈速。

  ![排行榜](media/vstu_azure-test-sample-game-image5.png)

## <a name="next-step"></a>下一步

* [RaceScene 说明](visual-studio-tools-for-unity-azure-racescene.md)
