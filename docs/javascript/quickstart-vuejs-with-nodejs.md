---
title: 快速入门：创建第一个 Vue.js 应用
description: 在此快速入门中，将使用针对 Visual Studio 的 Node.js 工具在 Visual Studio 中创建 Vue.js 应用
ms.custom: seodec18
ms.date: 09/24/2018
ms.prod: visual-studio-dev15
ms.technology: vs-nodejs
ms.topic: quickstart
ms.devlang: javascript
ms.assetid: b0e4ebed-1a01-41ef-aad1-4d8465ce5322
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 4f346f75078ff513dbbb91230d564686d6a1e023
ms.sourcegitcommit: a715de2ba8c703f37aa2102567b1aa2c0f05a117
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2018
ms.locfileid: "53441478"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-vuejs-app"></a>快速入门：使用 Visual Studio 创建第一个 Vue.js 应用

在这个对 Visual Studio 集成开发环境 (IDE) 的 5-10 分钟简介中，可以创建并运行简单的 Vue.js Web 应用程序。 如果尚未安装 Visual Studio 2017，请转到 [Visual Studio 下载](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)页免费安装。

> [!IMPORTANT]
> 本文需要从 Visual Studio 2017 版本 15.8 开始提供的 Vue.js 模板。

## <a name="create-a-project"></a>创建项目

首先，创建 Vue.js Web 应用程序项目。

1. 如果尚未安装 Node.js 运行时，请从 [Node.js](https://nodejs.org/en/download/) 网站安装 LTS 版本。

    一般情况下，Visual Studio 会自动检测已安装的 Node.js 运行时。 如果系统未检测到已安装运行时，则可以将项目配置为引用属性页中已安装的运行时（创建项目后，右键单击项目节点并选择“属性”）。

1. 打开 Visual Studio 2017。

1. 在顶部菜单栏，依次选择“文件” > “新建” > “项目”。

1. 在“新建项目”对话框中，在“JavaScript” > “Node.js”或“TypeScript” > “Node.js”下，选择“基本 Vue.js Web 应用程序”。 输入项目名称，然后单击“确定”。

     ![Vue.js 模板](../javascript/media/vuejs-template.png)

    Visual Studio 随即创建新项目。 新项目在“解决方案资源管理器”（右窗格）中打开。

     如果没有看到“基本 Vue.js Web 应用程序”项目模板，请单击“新建项目”对话框左侧窗格中的“打开 Visual Studio 安装程序”链接。 Visual Studio 安装程序启动。 选择“Node.js 开发”工作负载，然后选择“修改”。

     ![VS 安装程序中的 Node.js 工作负载](../ide/media/quickstart-nodejs-workload.png)

    Visual Studio 创建新的解决方案并打开项目。

1. 选中输出窗口（下方窗格），查看安装应用程序所需的 npm 包的进度。

1. 打开“解决方案资源管理器”中的“npm”节点，确保其中已安装所有列出的 npm 包。

    如果缺少任何包（感叹号图标），可右键单击“npm”节点并选择“安装缺少的 npm 包”。

## <a name="explore-the-ide"></a>探索 IDE

1. 查看右窗格中的“解决方案资源管理器”。

     ![Vue.js 解决方案](../javascript/media/vuejs-solution.png)

   - 粗体突出显示的是项目，其名称是在“新建项目”对话框中指定的名称。 在磁盘上，此项目由项目文件夹中的 .njsproj 文件表示。

   - 顶层是一个解决方案，它与项目默认同名。 解决方案（在磁盘上由 .sln 文件表示）是一个或多个相关项目的容器。

   - npm 节点显示任何已安装的 npm 包。 可以右键单击 npm 节点搜索 npm 包，并使用对话框安装 npm 包。

2. 如果想要从命令提示符安装 npm 包或运行 Node.js 命令，请右键单击项目节点，然后选择“在此处打开命令提示符”。

## <a name="add-a-vue-file-to-the-project"></a>向项目添加一个 .vue 文件

1. 在“解决方案资源管理器”中，右键单击任意文件夹（如 src/components 文件夹），然后选择“添加” > “新项”。

1. 选择“JavaScript 单个文件组件”或“TypeScript Vue 单个文件组件”，然后单击“添加”。

    Visual Studio 将向项目添加新文件。

## <a name="build-the-project"></a>生成项目

1. （仅限 TypeScript 项目）在 Visual Studio 中，选择“生成” > “清洁解决方案”。

1. 接下来，选择“生成” > “生成解决方案”以生成项目。 检查“输出”窗口以查看生成结果，并从“显示输出来源”列表中选择“生成”。

    Vue.js 项目模板通过配置后期生成事件来使用 `build` npm 脚本。 如果要修改此设置，在“Windows 资源管理器”中打开项目文件 (\<projectname\>.njsproj) 并找到下面的代码行：

    ```xml
    <PostBuildEvent>npm run build</PostBuildEvent>
    ```

## <a name="run-the-application"></a>运行此应用程序

1. 按 Ctrl+F5（或“调试”>“开始执行(不调试)”）运行应用程序。

   在控制台中，你将看到消息“正在启动开发服务器”。

   应用将在浏览器中打开。

   ![在浏览器中运行的 Vue.js 应用](../javascript/media/vuejs-running-app.png)

1. 关闭 Web 浏览器。

祝贺你完成此快速入门！ 希望你已对 Visual Studio IDE 和 Vue.js 有了一定了解。 若要深入了解其功能，请继续阅读目录中“教程”部分的教程。

## <a name="next-steps"></a>后续步骤

- 浏览 [Node.js 和 Express 教程](../nodejs/tutorial-nodejs.md)
- 浏览 [Node.js 和 React 教程](../nodejs/tutorial-nodejs-with-react-and-jsx.md)
- [将应用部署到 Linux 应用服务](../javascript/publish-nodejs-app-azure.md)