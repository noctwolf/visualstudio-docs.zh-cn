---
title: "Visual Studio Tools for Unity Azure 演练准备 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: B921C2AC-B5D6-4B24-918E-511F83D57275
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 92f85e39d0f643e896457cae48ab10aa0446dfcd
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="prepare-the-development-environment"></a>准备开发环境

在 Unity 中使用 Azure 移动客户端 SDK 有一些先决条件。

## <a name="download-and-install-unity-2017"></a>下载并安装 Unity 2017

需要 Unity 2017.1 或更高版本。 所有 Unity 计划都适用于本演练，包括免费个人计划。 从 https://store.unity.com/ 下载 Unity。

## <a name="download-and-install-visual-studio-2017"></a>下载并安装 Visual Studio 2017

本演练需要 Visual Studio 2017 15.3 及更高版本（具有“使用 Unity 的游戏开发”工作负荷）。 所有版本的 Visual Studio 2017 都适用于本演练，包括免费的 Community 版。

1. 从 https://www.visualstudio.com/ 下载 Visual Studio 2017。

2. 安装 Visual Studio 2017 并确保启用“使用 Unity 的游戏开发”工作负荷。

 ![选择 Unity 工作负荷](media/vstu_azure-prepare-dev-environment-image0.png)

 > [!NOTE]
 > 如果已安装 Visual Studio 2017，则可以通过运行 Visual Studio 安装程序来查看和修改工作负荷。

## <a name="create-a-new-3d-unity-project"></a>创建新 3D Unity 项目

启动 Unity 并创建新 3D 项目。

![创建新 Unity 项目](media/vstu_azure-prepare-dev-environment-image1.png)

## <a name="set-the-script-editor-to-visual-studio-preview-2017"></a>将脚本编辑器设置为 Visual Studio Preview 2017

你可能已将 Visual Studio 2017 设置为 Unity 的外部脚本编辑器，但务必要确保选择 15.3 预览版。

1. 在 Unity“编辑”菜单上，选择“编辑”>“首选项...”。

  ![打开“首选项”菜单](media/vstu_azure-prepare-dev-environment-image1.2.png)

2. 当“Unity 首选项”窗口弹出时，选择左侧的“外部工具”选项卡。

3. 在“外部脚本编辑器”下拉菜单中，选择“Visual Studio 2017”。

  ![设置外部脚本编辑器](media/vstu_azure-prepare-dev-environment-image3.png)

## <a name="change-the-unity-scripting-runtime-to-net-46"></a>将 Unity 脚本运行时更改为 .NET 4.6
本演练需要 .NET 4.6 才能使用 Azure 移动客户端 SDK 及其依赖项。

1. 在 Unity“文件”菜单上，选择“文件”>“生成设置...”。

  ![打开“生成设置”](media/vstu_azure-prepare-dev-environment-image4.png)

2. 单击“播放器设置...”按钮。

  ![打开“播放器设置”](media/vstu_azure-prepare-dev-environment-image5.png)

3. “播放器设置”会在 Unity 检查器窗口中打开。 在“配置”标题下，单击“脚本运行时版本”下拉列表，然后选择“实验(.NET 4.6 等效)”。 这会显示一个要求重新启动 Unity 的对话框。 选择“重新启动”。

  ![选择 .NET 4.6](media/vstu_azure-prepare-dev-environment-image6.png)

## <a name="add-a-reference-to-systemnethttpdll"></a>添加对 System.Net.Http.dll 的引用

Unity .NET 4.6 等效脚本运行时允许使用 Azure 移动客户端 SDK 所需的 System.Net.Http 包。 该 DLL 文件包含在 Unity 中，但是必须添加引用才能使用它。

1. 在 Unity 编辑器项目窗口中，**右键单击** **Assets** 文件夹，然后选择“在资源管理器中显示”。

  ![在资源管理器中显示 Assets 文件夹](media/vstu_azure-prepare-dev-environment-image7.png)

2. 在弹出的资源管理器窗口中，双击 **Assets** 目录以打开它。

3. 在 Assets 目录中，**右键单击**并选择“新建”>“文本文档”。

4. 在文本编辑器中打开新文本文档，然后添加行：`-r:System.Net.Http.dll`

5. 保存该文档并关闭。

4. 将新文本文档重命名为“**mcs.rsp**”并确保删除 .txt 文件扩展名。

  * 如果隐藏了文件扩展名，则需要更改文件夹查看选项以显示它们。
  * 打开“开始”菜单并输入“文件夹选项”以进行搜索。 选择“文件资源管理器选项”。
  * 选择“查看”选项卡，在高级设置中，确保取消选中“隐藏已知文件类型的扩展名”。

    ![在资源管理器中显示 Assets 文件夹](media/vstu_azure-prepare-dev-environment-image8.png)

完成这些步骤之后，你应在 Unity 项目的 **Assets** 根目录中具有一个名为 **mcs.rsp** 的文件，其中包含行 `r:System.Net.Http.dll`。

>[!NOTE]
> 引用功能需要 Visual Studio Tools for Unity 3.3 及更高版本（包含在 Visual Studio 15.3 + Unity 工作负荷中）。 如果此步骤并不适用于你，请确保你安装了正确版本的 VSTU。

## <a name="add-the-newtonsoftjson-nuget-package-to-your-project"></a>将 Newtonsoft.Json NuGet 包添加到项目

Azure 移动客户端 SDK 需要 Newtonsoft.Json 包。 遗憾的是，Unity 不支持 NuGet。 如果在 Visual Studio 中打开 Unity 项目并添加具有 NuGet 的包，则在你下次在 Unity 编辑器中打开该项目时，Unity 会擦除它。 但是，NuGet 中的包可以手动添加到 Unity 项目。

1. 在 Unity 项目的 Assets 目录中创建一个名为“**NuGet Packages**”的新文件夹。 这仅用于进行组织。

2. 转到 https://www.nuget.org/packages/Newtonsoft.Json/ 并单击“手动下载”按钮。 下载 .nupkg 文件。

  ![在资源管理器中显示 Assets 文件夹](media/vstu_azure-prepare-dev-environment-image9.png)

3. 找到新下载的文件并将文件扩展名从 .nupkg 更改为 **.zip**。 这应使你可以如同任何其他 zip 文件一样查看和提取包含文件。

4. 打开或提取 zip 目录并浏览到 **\lib\net45**。

5. 将 **Newtonsoft.Json.dll** 文件复制到 Unity 项目的 **Assets\NuGet Packages** 目录。

## <a name="add-the-azure-mobile-client-sdk-nuget-package-to-your-project"></a>将 Azure 移动客户端 SDK NuGet 包添加到项目

Azure 移动客户端 SDK 包含用于轻松读取和写入 Azure 简易表的函数。

1. 转到 https://www.nuget.org/packages/Microsoft.Azure.Mobile.Client/ 并单击“手动下载”按钮。 下载 .nupkg 文件。

2. 找到新下载的文件并将文件扩展名从 .nupkg 更改为 **.zip**。 这应使你可以如同任何其他 zip 文件一样查看和提取包含文件。

3. 打开或提取 zip 目录并浏览到 **\lib\net45**。

4. 将 **Microsoft.Azure.Mobile.Client.dll** 文件复制到 Unity 项目的 **Assets\NuGet Packages** 目录。

>[!WARNING]
> 完成这些步骤之后，请务必重新启动 Unity 和 Visual Studio，否则 InteliSense 可能无法识别新添加的包。

## <a name="conclusion"></a>结束语

完成这些步骤之后，Unity 项目应设置为使用 Azure 移动客户端 SDK。 可以测试部署环境，具体方法是在 Unity 项目中创建新 C# 脚本，在 Visual Studio 中打开它，并在顶部输入以下 using 语句：
```
using System.Net.Http;
using Newtonsoft.Json;
using Microsoft.WindowsAzure.MobileServices;
```

如果 InteliSense 检测到这些 using 语句，则设置已正确完成。 如果有任何错误或 InteliSense 无法识别这些包，请尝试重新启动 Unity 和 Visual Studio。 如果它仍不起作用，请重新访问以上步骤。

## <a name="next-step"></a>下一步

* [创建数据模型类](visual-studio-tools-for-unity-azure-data.md)
