---
title: "Visual Studio Tools for Unity Azure 演练 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7921D4C7-5526-42F5-8E03-82D3E33A893F
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: a7e12508537a3bcda1df7997ba9e390b75b9beaf
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="using-azure-easy-tables-with-unity-walkthrough"></a>将 Azure 简易表与 Unity 结合使用的演练

![示例游戏屏幕截图](media/vstu_azure-test-sample-game-image2.png)

## <a name="introduction"></a>介绍

Azure 提供将遥测和其他游戏数据存储在云中的可缩放解决方案。 随着 Unity 2017 的发布，Unity 对 .NET 4.6 的支持允许使用 Azure 移动客户端 SDK，从而使 Azure 集成比以往更加简单。

这些步骤将指导完成以下过程：设置利用 Azure 将遥测和排行榜数据存储在云中的 Unity 项目。

> [!NOTE]
> 此项目需要 Unity 2017 中的“实验”.NET 4.6 Mono 脚本运行时。 [Unity 声称这很快将成为默认设置](https://forum.unity3d.com/threads/future-plans-for-the-mono-runtime-upgrade.464327/)，但是目前它仍然标记为“实验”，你可能会遇到问题。

> 本演练介绍一个从 Unity PC 内部版本连接到 Azure 移动应用后端的示例。 撰写本文档时，存在一些阻止此项目在 Mac 和 Android 平台上正常运行的已知问题。 虽然这些已知问题将得到解决，但是日程表不确定。 有关详细信息，请访问 Unity [实验脚本论坛](https://forum.unity3d.com/forums/experimental-scripting-previews.107/)。

## <a name="download-the-completed-project"></a>下载已完成的项目

GitHub 上提供了已完成的项目。 但是，本演练假设你是从空的新项目开始，会在需要时提供用于下载资产的链接。

## <a name="walkthrough-steps"></a>演练步骤

1. [在 Azure 中配置简易表](visual-studio-tools-for-unity-azure-configure.md)
2. [创建简易表](visual-studio-tools-for-unity-azure-setup.md)
3. [准备开发环境](visual-studio-tools-for-unity-azure-prepare.md)
4. [创建数据模型类](visual-studio-tools-for-unity-azure-data.md)
5. [实现 Azure MobileServiceClient](visual-studio-tools-for-unity-azure-mobile-client.md)
6. [更新 Unity Mono 安全证书存储](visual-studio-tools-for-unity-azure-security.md)
7. [测试客户端连接](visual-studio-tools-for-unity-azure-connection.md)
7. [导入示例游戏资产](visual-studio-tools-for-unity-azure-game-assets.md)
8. [测试示例游戏](visual-studio-tools-for-unity-azure-game.md)
9. [RaceScene 说明](visual-studio-tools-for-unity-azure-racescene.md)
10. [HeatmapScene 说明](visual-studio-tools-for-unity-azure-heatmapscene.md)
11. [LeaderboardScene 说明](visual-studio-tools-for-unity-azure-leaderboardscene.md)


## <a name="next-step"></a>下一步
* [在 Azure 中配置简易表](visual-studio-tools-for-unity-azure-configure.md)
