---
title: 在 Visual Studio for Mac 中编译和生成
description: ''
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: FB253757-DB00-4889-A6BF-E44722E25BD1
ms.openlocfilehash: 7a7dfaeca45ae157dc9e82b9f8eff54244cbd7ca
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="compiling-and-building-in-visual-studio-for-mac"></a>在 Visual Studio for Mac 中编译和生成

Visual Studio for Mac 可用于在项目开发过程中生成应用程序和创建程序集。 请务必提早且经常编译和生成代码，以便确定类型不匹配和其他编译时错误。

## <a name="building-from-the-ide"></a>从 IDE 生成

使用 Visual Studio for Mac，可立即创建和运行生成，并保持对生成功能的控制。 Visual Studio for Mac 使用 MSBuild 作为基础生成系统。

在 IDE 中创建的所有项目和解决方案都拥有一个默认生成配置，该配置定义生成的上下文。 可编辑这些配置，也可创建自己的配置。 创建或修改这些配置会自动更新项目文件，之后 MSBuild 会使用该文件生成项目。  

有关如何在 IDE 中生成项目和解决方案的详细信息，请参阅[生成和清理项目和解决方案](~/building-and-cleaning-projects-and-solutions.md)指南。

Visual Studio for Mac 还可用于执行以下操作：

* 更改输出路径。 可在项目选项中进行编辑：

    ![更改输出路径](media/compiling-and-building-image4.png)

* 更改生成输出的详细级别：

    ![更改生成的详细级别](media/compiling-and-building-image5.png)

* 在生成或清理之前、之后或者生成或清理过程中添加自定义命令：

    ![添加自定义命令](media/compiling-and-building-image6.png)

## <a name="building-from-command-line"></a>从命令行生成

可使用 MSBuild 生成引擎通过命令行生成应用程序。

请参阅 [MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild) 内容，了解有关使用 MSBuild 的详细信息。

## <a name="building-from-visual-studio-team-services"></a>从 Visual Studio Team Services 生成

* [生成 Xamarin 应用](https://www.visualstudio.com/docs/build/apps/mobile/xamarin)
* [与 Xamarin 持续集成](https://developer.xamarin.com/guides/cross-platform/ci/)