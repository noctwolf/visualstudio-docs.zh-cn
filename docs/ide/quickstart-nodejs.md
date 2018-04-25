---
title: 快速入门：使用 Visual Studio 创建第一个 Node.js 应用 | Microsoft Docs
description: 本快速入门中，将在 Visual Studio 中创建 Node.js 应用
ms.custom: ''
ms.date: 11/15/2017
ms.technology:
- vs-acquisition
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
ms.openlocfilehash: c1c40d3d62abb855906b7b61a75c698d21622d1d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="quickstart-use-visual-studio-to-create-your-first-nodejs-app"></a>快速入门：使用 Visual Studio 创建第一个 Node.js 应用
在这个对 Visual Studio 集成开发环境 (IDE) 的 5-10 分钟简介中，可以创建简单的 Node.js Web 应用程序。 如果尚未安装 Visual Studio，请在[此处](http://www.visualstudio.com)免费安装。  

## <a name="create-a-project"></a>创建项目
首先，创建 Node.js Web 应用程序项目。

1. 如果尚未安装 Node.js 运行时，请从 [Node.js](https://nodejs.org/en/download/) 网站安装 LTS 版本。

    一般情况下，Visual Studio 会自动检测已安装的 Node.js 运行时。 如果没有检测到已安装的运行时，则可配置项目来引用已安装的运行时。

1. 打开 Visual Studio 2017。  

1. 在顶部菜单栏，依次选择“文件” > “新建” > “项目...”。  

1. 在“新建项目”对话框的左窗格中，展开“JavaScript”，然后选择“Node.js”。 在中间窗格中，选择“空 Node.js Web 应用程序”，然后选择“确定”。   

     如果没有看到“空白 Node.js Web 应用程序”项目模板，请单击“新建项目”对话框左侧窗格中的“打开 Visual Studio 安装程序”链接。 Visual Studio 安装程序启动。 选择“Node.js 开发”工作负载，然后选择“修改”。  

     ![VS 安装程序中的 Node.js 工作负载](../ide/media/quickstart-nodejs-workload.png)  

    Visual Studio 创建新的解决方案并打开项目。 server.js 在位于左侧窗格的编辑器中打开。

## <a name="explore-the-ide"></a>探索 IDE  

1. 查看右窗格中的“解决方案资源管理器”。

   ![“解决方案资源管理器”](../ide/media/quickstart-nodejs-solution-explorer.png)  

  - 粗体突出显示的是项目，其名称是在“新建项目”对话框中指定的名称。 在磁盘上，此项目由项目文件夹中的 .njsproj 文件表示。

  - 顶层是一个解决方案，它与项目默认同名。 解决方案在磁盘上由 .sln 文件表示，是一个或多个相关项目的容器。

  - Npm 节点显示任何已安装的 npm 包。 可以右键单击 npm 节点搜索 npm 包，并使用对话框安装 npm 包。

1. 如果想要从命令提示符安装 npm 包或 node.js 命令，请右键单击项目节点，然后选择“在此处打开命令提示符”。

   ![Node.js 命令提示符](../ide/media/quickstart-nodejs-command-prompt.png) 

1. 在编辑器（左窗格）的 server.js 文件中，选择 `http.createServer`然后按 F12 或选择上下文菜单（右键单击菜单）中的“转到定义”。 此命令将转到 index.d.ts 中 `createServer` 函数的定义。  

   ![转到定义上下文菜单](../ide/media/quickstart-nodejs-gotodefinition.png)  

1. 返回 server.js，然后将光标置于此代码行 `res.end('Hello World\n');` 中字符串的末尾处，并对其进行如下修改：

    `res.end('Hello World\n' + res.connection.`

    IntelliSense 会在键入 `connection.` 的位置提供选项，自动完成代码输入。

   ![IntelliSense 自动完成](../ide/media/quickstart-nodejs-intellisense.png)  

1. 选择“localPort”，然后键入 `);` 完成该语句，使其如下所示：

    `res.end('Hello World\n' + res.connection.localPort);`

## <a name="run-the-application"></a>运行此应用程序
1. 按 Ctrl+F5（或“调试”>“开始执行(不调试)”）运行应用程序。 应用将在浏览器中打开。  

1. 在浏览器窗口中，将看到“Hello World”以及本地端口号。

1. 关闭 Web 浏览器。  

祝贺你完成此快速入门！ 我们希望你已对 Visual Studio IDE 有了一定了解。 若要深入了解其功能，请继续阅读目录中“教程”部分的教程。  

## <a name="next-steps"></a>后续步骤 

- 浏览 [Node.js 和 Express 教程](../nodejs/tutorial-nodejs.md)  
- 浏览 [Node.js 和 React 教程](../nodejs/tutorial-nodejs-with-react-and-jsx.md)  