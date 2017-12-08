---
title: "Visual Studio Tools for Unity Azure 演练游戏资产 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: C06FAB2E-F592-4EFF-B96A-58858C92DCEB
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 3b1ad3d7dc6af48986e8b10278a8b8135843239d
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="import-sample-game-assets"></a>导入示例游戏资产

已对核心功能进行测试，证实它可以正常工作，现在开始导入示例游戏资产。

## <a name="import-package"></a>导入程序包

1. 下载[示例游戏资产程序包](https://github.com/dantogno/UnityAzureSample/blob/master/Azure%20Easy%20tables%20sample%20game%20assets.unitypackage)。

2. 确保 Unity 项目已打开，然后导航到下载位置并双击文件。 随即将在 Unity 中打开导入对话框。

3. 单击“全部”，然后单击“导入”。 等待生成的进度条完成。

  ![导入程序包](media/vstu_azure-import-sample-assets-image1.png)

## <a name="add-scenes-to-build-settings"></a>添加场景以生成设置

导入完文件后，必须在 Unity 项目的生成设置中添加所需的场景文件。

1. 在 Unity 项目窗口中，导航到 **Azure Easy Tables sample game assets/Scenes** 目录。

2. 从 Unity 菜单中选择“文件”>“生成设置...”。随即显示“生成设置”对话框。

3. 将项目窗口中的 **HeatmapScene**、**LeaderboardScene**、**MenuScene** 和 **RaceScene** 文件拖到“生成设置”对话框的“生成中的场景”部分。

  ![导入程序包](media/vstu_azure-import-sample-assets-image2.png)

4. 从 Unity 菜单中选择“文件”>“保存项目”，确保保存生成设置。

## <a name="next-step"></a>下一步

* [测试示例游戏](visual-studio-tools-for-unity-azure-game.md)