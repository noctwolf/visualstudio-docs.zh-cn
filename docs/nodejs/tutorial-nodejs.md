---
title: "Visual Studio 中的 Node.js 入门 | Microsoft Docs"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: ghogen
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: a8e6c800ef036d0f6e8e5affae745e541a276284
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="getting-started-with-nodejs-in-visual-studio"></a>Visual Studio 中的 Node.js 入门
本教程介绍使用 Visual Studio 进行 Node.js 开发，将创建一个简单的 Node.js Web 应用，添加一些代码，浏览 IDE 的某些功能并运行应用。 如果尚未安装 Visual Studio，请在[此处](http://www.visualstudio.com)免费安装。  

## <a name="create-a-project"></a>创建项目
首先，创建 Node.js Web 应用程序项目。

1. 打开 Visual Studio 2017。  

2. 在顶部菜单栏，依次选择“文件” > “新建” > “项目...”。  

3. 在“新建项目”对话框的左窗格中，展开“JavaScript”，然后选择“Node.js”。 在中间窗格中，选择“基本 Azure Node.js Express 4 应用程序”，然后选择“确定”。   

     如果没有看到“基本 Azure Node.js Express 4 应用程序”项目模板，请单击“新建项目”对话框左侧窗格中的“打开 Visual Studio 安装程序”链接。 Visual Studio 安装程序启动。 选择“Node.js 开发”工作负载，然后选择“修改”。 

    Visual Studio 创建新的解决方案并打开项目。 在编辑器（左窗格）中打开 App.js 项目文件。 如果不熟悉 Visual Studio 解决方案和项目，请参阅[快速入门：使用 Visual Studio 创建第一个 Node.js 应用](../ide/quickstart-nodejs.md)。

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

1. 在 `data` 后键入 `: get`，IntelliSense 将显示 getData 函数。 选择 `getData`。

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

1. 按 Ctrl+F5 运行应用程序。

    调试器会在设置的断点处暂停。 现在，可以检查应用状态。

1. 将鼠标悬停在 `getData` 上，查看其在数据提示中的属性

    ![检查变量](../nodejs/media/tutorial-nodejs-inspect-variables.png)

1. 按 F5 继续。

    应用将在浏览器中打开。

    在浏览器窗口中，将看到“Express”为标题，“Welcome to Express”位于第一个段。

1. 单击这些按钮可显示不同的图像。

    ![在浏览器中运行应用](../nodejs/media/tutorial-nodejs-running-in-browser.png)  

1. 选择“视图”>“其他窗口”>“Node.js 交互式窗口”，打开 Node.js 交互式窗口。

   ![打开 Node.js 交互式窗口](../nodejs/media/tutorial-nodejs-interactive-window.png)  

    交互式窗口支持可采用代码执行的所有操作，包括使用 `require()` 语句。 以下屏幕截图中的代码定义一个变量，并显示 Node.js 解释器的位置。

   ![Node.js 交互式窗口](../nodejs/media/tutorial-nodejs-interactive-window-example.png)  

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

- 详细了解[针对 Visual Studio 的 Node.js 工具](https://github.com/Microsoft/nodejstools/wiki)  
- 详细了解 [Visual Studio IDE](../ide/visual-studio-ide.md)  