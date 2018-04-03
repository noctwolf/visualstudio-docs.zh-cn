---
title: 创建 Node.js 和 Express 应用 - Visual Studio | Microsoft Docs
description: 本教程会在 Visual Studio 中创建 Node.js 和 Express 应用
ms.custom: ''
ms.date: 03/13/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-nodejs
ms.tgt_pltfrm: ''
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: ghogen
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 1ababcbc0903d474c2992b68e3571a71c4e88d99
ms.sourcegitcommit: fb1fede41d8c5e459dd222755b0497b9d361bc51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="tutorial-create-a-nodejs-and-express-app-in-visual-studio"></a>教程：在 Visual Studio 中创建 Node.js 和 Express 应用
本教程介绍如果使用 Node.js 和 Express 进行 Visual Studio 开发，教程会创建一个简单的 Node.js Web 应用，添加一些代码，浏览 IDE 的某些功能并运行应用。 如果尚未安装 Visual Studio，请在[此处](http://www.visualstudio.com)免费安装。  

在本教程中，你将了解：
> [!div class="checklist"]
> * 创建 Node.js 项目
> * 添加一些代码
> * 使用 IntelliSense
> * 运行应用
> * 命中断点

## <a name="prerequisites"></a>系统必备

* 须安装 Visual Studio 且具有 Node.js 开发工作负载。

    如果尚未安装 Visual Studio，请在[此处](http://www.visualstudio.com)免费安装。

    如果需要安装工作负载，但已有 Visual Studio，则单击“新建项目”对话框左窗格中的“打开 Visual Studio 安装程序”链接。 Visual Studio 安装程序启动。 选择“Node.js 开发”工作负载，然后选择“修改”。

* 须安装 Node.js 运行时。

    如果未安装，请从 [Node.js](https://nodejs.org/en/download/) 网站安装 LTS 版本。 一般情况下，Visual Studio 会自动检测已安装的 Node.js 运行时。 如果系统未检测到已安装运行时，则可以将项目配置为引用属性页中已安装的运行时（创建项目后，右键单击项目节点并选择“属性”）。

    本教程已使用 Node.js 8.10.0 进行测试。

## <a name="create-a-project"></a>创建项目
首先，创建 Node.js Web 应用程序项目。

1. 打开 Visual Studio 2017。  

1. 在顶部菜单栏，依次选择“文件” > “新建” > “项目...”。  

1. 在“新建项目”对话框的左窗格中，展开“JavaScript”，然后选择“Node.js”。 在中间窗格中，选择“基本 Azure Node.js Express 4 应用程序”，然后选择“确定”。   

     如果未看到“基本 Azure Node.js Express 4 应用程序”项目模板，须先安装 Node.js 开发工作负载。 

    Visual Studio 创建新的解决方案并打开项目。 在编辑器（左窗格）中打开 App.js 项目文件。

    - 粗体突出显示的是项目，其名称是在“新建项目”对话框中指定的名称。 在文件系统中，此项目由项目文件夹中的 .njsproj 文件表示。 可以右键单击项目并选择“属性”，设置与项目相关的属性和环境变量。 可以使用其他开发工具执行往返，因为项目文件不对 Node.js 项目源做出自定义更改。

    - 顶层是一个解决方案，它与项目默认同名。 解决方案在磁盘上由 .sln 文件表示，是一个或多个相关项目的容器。

    - Npm 节点显示任何已安装的 npm 包。 可以右键单击 npm 节点搜索 npm 包，并使用对话框安装 npm 包。

    - 项目文件（例如 app.js）显示在项目节点下。 app.js 是项目启动文件。

1. 打开“npm”节点，确保其中存在所有必需的 npm 包。

    如果有丢失的包（感叹号图标），可右键单击“npm”节点，然后选择“安装丢失的 npm 包”。

## <a name="add-some-code"></a>添加一些代码

1. 在解决方案资源管理器（右窗格）中，打开“视图”文件夹，然后打开 index.pug。

1. 将内容替换为以下标记。

    ```js
    extends layout

    block content
      h1= title
      p Welcome to #{title}
      script.
        var f1 = function() { document.getElementById('myImage').src='#{data.item1}' }
      script.
        var f2 = function() { document.getElementById('myImage').src='#{data.item2}' }
      script.
        var f3 = function() { document.getElementById('myImage').src='#{data.item3}' }

      button(onclick='f1()') One!
      button(onclick='f2()') Two!
      button(onclick='f3()') Three!
      p
      a: img(id='myImage' height='200' width='200' src='')
    ```

1. 在“路由”文件夹中，打开 index.js。

1. 在 `router.get` 的调用前添加以下代码：

    ```js
    var getData = function () {
        var data = {
            'item1': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-76.jpg',
            'item2': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-77.jpg',
            'item3': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-78.jpg'
        }
        return data;
    }
    ````

1. 使用以下代码替换 `router.get` 函数调用：

    ```js
    router.get('/', function (req, res) {
        res.render('index', { title: 'Express', "data" });
    });
    ```

    包含 `res.render` 的代码行中存在错误。 在应用可以运行前需要修复此错误。 下一节将修复此错误。

## <a name="use-intellisense"></a>使用 IntelliSense

1. 在 index.js 中，转到包含 `res.render` 的代码行。

1. 在 `data` 字符串后键入 `: get`，IntelliSense 将显示 `getData` 函数。 选择 `getData`。

    ![使用 IntelliSense](../nodejs/media/tutorial-nodejs-intellisense.png) 

1. 删除 `"data"` 前的逗号 (`,`)，将看到针对该表达式的绿色语法突出显示。 将鼠标悬停在语法突出显示上。

    ![查看语法错误](../nodejs/media/tutorial-nodejs-syntax-checking.png) 

    此消息的最后一行告诉你，JavaScript 解释器需要一个逗号 (`,`)。

1. 单击“错误列表”选项卡。

    可看到警告和描述，以及文件名和行号。

    ![查看错误列表](../nodejs/media/tutorial-nodejs-error-list.png)

1. 在 `"data"` 前添加逗号 (`,`)，修复代码。

## <a name="set-a-breakpoint"></a>设置断点

1. 在 index.js 中，单击以下代码行前左测的装订线，设置一个断点：

    `res.render('index', { title: 'Express', "data": getData() });`

    断点是可靠调试的最基本和最重要的功能。 断点指示 Visual Studio 应在哪个位置挂起你的运行代码，以使你可以查看变量的值或内存的行为，或确定代码的分支是否运行。 

    ![设置断点](../nodejs/media/tutorial-nodejs-set-breakpoint.png) 

## <a name="run-the-application"></a>运行此应用程序

1. 在调试工具栏中选择调试目标。

    ![选择调试目标](../nodejs/media/tutorial-nodejs-deploy-target.png) 

1. 按 F5（“调试” > “启动调试”）来运行该应用程序。

    调试器会在设置的断点处暂停。 现在，可以检查应用状态。

1. 将鼠标悬停在 `getData` 上，查看其在数据提示中的属性

    ![检查变量](../nodejs/media/tutorial-nodejs-inspect-variables.png)

1. 按 F5（“调试” > “继续”）继续。

    应用将在浏览器中打开。

    在浏览器窗口中，将看到“Express”为标题，“Welcome to Express”位于第一个段。

1. 单击这些按钮可显示不同的图像。

    ![在浏览器中运行应用](../nodejs/media/tutorial-nodejs-running-in-browser.png)  

1. 关闭 Web 浏览器。  

## <a name="optional-publish-to-azure-app-service"></a>（可选）发布到 Azure 应用服务

1. 在解决方案资源管理器中，右键单击项目，选择“发布”。

   ![发布到 Azure 应用服务](../nodejs/media/tutorial-nodejs-publish-to-azure.png)  

1. 选择“Microsoft Azure 应用服务”。

    在“应用服务”对话框中，可登录 Azure 帐户并连接到现有的 Azure 订阅。

1. 按其余步骤来选择订阅、选择或创建资源组、选择或创建应用服务计划，然后在系统提示发布到 Azure 时按照步骤操作。 有关更详细的说明，请参阅 [Publish to Azure Website using Web Deploy](https://github.com/Microsoft/nodejstools/wiki/Publish-to-Azure-Website-using-Web-Deploy)（使用 Web 部署发布到 Azure 网站）。

1. “输出”窗口显示部署到 Azure 的进度。

    成功部署后，应用将在 Azure 应用服务中运行的浏览器中打开。 单击按钮可显示图像。

   ![Azure 应用服务中运行的应用](../nodejs/media/tutorial-nodejs-running-in-azure.png)  

恭喜你完成本教程！

## <a name="next-steps"></a>后续步骤 

本教程介绍了如何使用 Express 创建和运行 Node.js 应用和使用调试程序命中断点。

> [!div class="nextstepaction"]
> [适用于 Visual Studio 的 Node.js 工具](https://github.com/Microsoft/nodejstools)