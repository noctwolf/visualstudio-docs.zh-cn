---
title: "快速入门：使用 Visual Studio 创建第一个 Python Web 应用 | Microsoft Docs"
ms.custom: 
ms.date: 12/1/2017"
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
ms.devlang: python
author: kraigb
ms.author: kraigb
manager: ghogen
dev_langs: python
ms.workload: python
ms.openlocfilehash: bf0a6e187a98a03d3beed33537fe5244ecd5d35d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-use-visual-studio-to-create-your-first-python-web-app"></a>快速入门：使用 Visual Studio 创建第一个 Python Web 应用

在这个对 Visual Studio 集成开发环境 (IDE) 的 5-10 分钟简介中，可以创建简单的 Python Web 应用程序。 如果尚未安装 Visual Studio，请在[此处](http://www.visualstudio.com)免费安装。

## <a name="create-the-project"></a>创建项目

1. 打开 Visual Studio 2017。

1. 在顶部菜单栏上，选择“文件”>“新建”>“项目...”。

1. 在“新建项目”对话框的左窗格中，展开“其他语言”，然后选择“Python”。 在中间窗格中，选择“Web 项目”，为项目命名（如“HelloPython”），然后选择“确定”。

    如果没有看到 Python 项目模板，取消“新建项目”对话框，然后在顶部菜单栏中选择“工具”>“获取工具和功能...”打开 Visual Studio 安装程序。 选择“Python 开发”工作负载，然后选择“修改”。

    ![Visual Studio 安装程序中的 Python 开发工作负载](../python/media/installation-python-workload.png)

1. 新项目在“解决方案资源管理器”的右窗格中打开。 项目此时已为空，因为它不含其他文件。

    ![显示新创建的空项目的解决方案资源管理器](media/quickstart-python-01-empty-project.png)

## <a name="install-the-falcon-library"></a>安装 Falcon 库

Python 中的 Web 应用几乎总是使用众多可用 Python 库中的一个来处理低级别详细信息，如路由 Web 请求和调整响应。 Visual Studio 中的 Python 开发工作负载提供围绕 Bottle、Flask 和 Django 库生成的[各种 Web 应用模板](../python/template-web.md)。

但在本快速入门中，将使用不同的库 [Falcon](https://falconframework.org/)，体验从头安装包和创建 Web 应用的过程。 为简单起见，以下步骤将 Falcon 安装到默认全局环境中。

1. 展开项目中的“Python 环境”节点，查看项目的默认环境。

    ![显示默认环境的解决方案资源管理器](media/quickstart-python-02-default-environment.png)

1. 右键单击环境，选择“安装 Python 包...”。此命令将打开“包”选项卡上的“Python 环境”窗口。在搜索字段中输入“falcon”，选择“PyPI 中的‘pip install falcon’”。 接受任何管理员权限提示，查看 Visual Studio 中的“输出”窗口了解进度。

    ![正在安装 Falcon 库](media/quickstart-python-03-install-package.png)

1. 安装完成后，库显示在“解决方案资源管理器”的环境中，这意味着可以在 Python 代码中使用它。

    ![安装的 falcon 库](media/quickstart-python-04-package-installed.png)

请注意，开发人员通常会创建一个“虚拟环境”用于安装特定项目的库，而不是在全局环境中安装库。 Visual Studio 中的许多 Python 项目模板都包含 `requirements.txt` 文件，该文件列出了模板所依赖的库。 从其中一个模板创建项目会触发创建用于安装库的虚拟环境。 有关详细信息，请参阅 [Python 环境 - 虚拟环境](../python/python-environments.md#virtual-environments)。

## <a name="add-a-code-file"></a>添加代码文件

现已准备好添加一点 Python 代码来实现最小的 Web 应用。

1. 在“解决方案资源管理器”中右键单击该项目，然后选择“添加”>“新建项...”。在出现的对话框中，选择“空 Python 文件”，将其命名为 `hello.py`，然后选择“确定”。 Visual Studio 会自动在编辑器窗口中打开该文件。 （通常情况下，“添加”>“新建项...”命令非常适合用来将不同种类的文件添加到项目中，因为项模板常提供有用的 Boilerplate 代码。）

1. 将代码复制粘贴或输入到 `hello.py` 中：

    ```python
    import falcon
    api = falcon.API()

    # In Falcon, define a class for each resource; the on_get 
    # method then handles any GET requests.

    class HelloResource:
        def on_get(self, req, resp):
            resp.status = falcon.HTTP_200  # 200 is the default
            resp.body = "Hello, Python!"

    # Resources are represented by long-lived class instances
    hello = HelloResource()

    # Instruct Falcon to route / and /hello to the HelloResource
    api.add_route('/', hello)
    api.add_route('/hello', hello)

    if __name__ == "__main__":
        from wsgiref.simple_server import make_server

        # Run the web server on localhost:8080
        print("Starting web app server")
        srv = make_server('localhost', 8080, api)
        srv.serve_forever()
    ```

有关 Falcon 的详细信息，请参阅 [Falcon 快速入门](https://falcon.readthedocs.io/en/stable/user/quickstart.html) (falcon.readthedocs.io)。

## <a name="run-the-application"></a>运行此应用程序

1. 在“解决方案资源管理器”中右键单击 `hello.py`，然后选择“设置为启动文件”。 该命令标识代码文件，使其在运行应用时在 Python 中启动。

1. 右键单击“解决方案资源管理器”中的“Hello Python”项目，然后选择“属性”。 然后选择“调试”选项卡并将“端口号”属性设置为 `8080`。 此步骤可确保 Visual Studio 使用 `localhost:8080` 而非随机端口来启动浏览器。

1. 选择“调试”>“开始执行(不调试)”(Ctrl+F5)，将更改保存至文件并运行应用。

1. 命令窗口中会显示消息“正在启动 Web 应用服务器”，然后浏览器窗口打开至 `localhost:8080`，可在其中看到消息“Hello, Python!” 命令窗口中还会显示 GET 请求。 （如果只在命令窗口中看到 Python 交互式 shell，或者如果该窗口在屏幕上短暂地闪烁，请确保在上述第 1 步中将 `hello.py` 设为启动文件。）

1. 关闭命令窗口，停止此应用。

## <a name="next-steps"></a>后续步骤

恭喜完成本快速入门，你已对 Visual Studio IDE 与 Python 有了些许了解。 若要继续在 Visual Studio 中了解更完整的 Python 教程（包括使用交互式窗口、调试、数据可视化效果以及使用 Git），请选择下面的按钮。

> [!div class="nextstepaction"]
> [教程：Visual Studio 中的 Python 入门](../python/vs-tutorial-01-01.md)。

- 了解 [Visual Studio 中的 Python Web 应用模板](../python/template-web.md)
- 详细了解 [Visual Studio IDE](../ide/visual-studio-ide.md)
- 了解如何使用 [Visual Studio 调试器](../debugger/debugger-feature-tour.md)