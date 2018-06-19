---
title: 使用 Visual Studio 在云中创建 .NET Core 开发环境（使用 Kubernetes 管理其中的容器）- 第 6 步 - 了解团队开发 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 04/05/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: b4bc1f44e63614346f4e2d149e76becabdcb8c71
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31899409"
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>开始使用 .NET Core 和 Visual Studio 通连环境

上一步：[调用另一个容器](get-started-netcore-visualstudio-05.md)

## <a name="learn-about-team-development"></a>了解团队开发

到目前为止，我们已经运行了应用程序代码，但感觉我们像是应用的唯一开发者。 在本节中，我们将介绍通连环境如何实现简化团队开发过程：
* 让开发者团队能够在相同的开发环境中工作。
* 让每位开发者都能够独立地迭代自己的代码，无需担心会破坏他人的代码。
* 在代码提交之前进行端到端的代码测试，无需创建模拟或模拟依赖项。

## <a name="challenges-with-developing-microservices"></a>开发微服务的挑战
我们的示例应用程序目前并不十分复杂。 但是在实际开发中，由于会添加更多的服务以及开发团队不断发展壮大，很快会涌现出新的挑战。

想象一下自己正在处理一项与众多其他服务进行交互的服务。

1. 将所有内容都放在本地开发是不现实的。 你的开发计算机可能不具备可以运行整个应用的足够资源。 或者，也许你的应用具有需要可公开访问的终结点（例如，应用会响应来自 SaaS 应用的 Webhook）。
1. 可以尝试只运行你所依赖的服务，但这意味着需要知道依赖项的完全闭包（例如，依赖项的依赖项）。 或者，问题在于因为没有亲自操作，而无法轻松了解如何生成和运行依赖项。
1. 某些开发者会诉诸于模拟自己的许多服务依赖项。 这种方式有时能起到一些作用，但管理这些模拟很快就会成为自身的开发负担。 此外，这会导致开发环境与生产看上去相差甚远，同时可能会悄悄引入许多细小的错误。
1. 这使得执行任何类型的端到端测试都变得困难。 实际上，集成测试只能发生在提交后，这意味着在开发周期的后期会遇到问题。

    ![](media/microservices-challenges.png)

## <a name="work-in-a-shared-development-environment"></a>在共享开发环境下工作
借助通连环境，可在 Azure 中设置共享开发环境。 每位开发者都可以专注于自己负责的应用程序部分，并可以在已包含其方案所依赖的所有其他服务和云资源的环境中迭代开发预提交代码。 依赖项始终保持最新，开发者能够以真实反映生产的方式进行工作。

## <a name="work-in-your-own-space"></a>在私有空间内工作
为服务开发代码时，在准备好签入代码之前，代码往往未处于良好状态。 仍需要对代码进行反复地修改测试并试验解决方案。 通连环境提供了空间的概念，可让你独立工作，无需担心会破坏团队成员的工作成果。

请执行以下操作，确保 `webfrontend` 和 `mywebapi` 服务在开发环境和 `mainline` 空间中运行。
1. 关闭两个服务的所有 F5/调试会话，但仍在 Visual Studio 窗口中打开项目。
2. 切换到 `mywebapi` 项目的 Visual Studio 窗口，然后按 Ctrl+F5 运行未附带调试程序的服务
3. 切换到 `webfrontend` 项目的 Visual Studio 窗口，然后按 Ctrl+F5 运行该项目。

> [!Note]
按 Ctrl+F5 后若出现初始显示的网页，有时需要刷新浏览器。

任何打开公共 URL 并导航到 Web 应用的人都会调用我们编写的代码路径，该路径使用默认的 `mainline` 空间通过这两个服务运行。 现在，假设我们要继续开发 `mywebapi` - 要继续开发同时不打断正在使用开发环境的其他开发者应该怎么办？ 为此，我们需要设置私有空间。

### <a name="create-a-new-space"></a>创建新空间
在 Visual Studio 中，可创建其他空间，以便在对服务执行 F5 或 Ctrl+F5 操作时使用。 可以将空间命名为任何名称，灵活地表达它的含义（例如， `sprint4` 或 `demo`）。

要创建新空间，请执行以下操作：
1. 切换到 `mywebapi` 项目的 Visual Studio 窗口。
2. 右键单击“解决方案资源管理器”中的项目，然后选择“属性”。
3. 选择左侧的“调试”选项卡，显示通连环境设置。
4. 可从此处更改或创建通连环境和/或在执行 F5 或 Ctrl+F5 操作时使用的空间。 确保选择之前创建的通连环境。
5. 在“空间”下拉列表中，选择“<新建空间...>”。

    ![](images/Settings.png)

6. 在“添加空间”对话框中，键入空间名称，然后单击“确定”。 我使用了我的名字作为新空间的名称，以便我的同事可以认出这是我工作的空间。

    ![](images/AddSpace.png)

7. 现在，应可在项目属性页上看到开发环境和选择的新空间。

    ![](images/Settings2.png)

### <a name="update-code-for-mywebapi"></a>更新 mywebapi 的示例代码

1. 在 `mywebapi` 项目中，对 `ValuesController.cs` 文件中的 `string Get(int id)` 方法执行代码更改，如下所示：
 
    ```csharp
    [HttpGet("{id}")]
    public string Get(int id)
    {
        return "mywebapi now says something new";
    }
    ```

2. 在这个更新的代码块中设置一个断点（之前可能已设置一个断点）。
3. 按 F5 启动 `mywebapi` 服务。 这可使用所选空间（本例中为 `scott`）在开发环境中启动该服务。

下面的图表可帮助理解不同空间的工作方式。 蓝色路径显示通过 `mainline` 空间发出的请求，如果没有将空间追加到 URL 的前面，则默认使用该路径。 绿色路径显示通过 `scott` 空间发出的请求。

![](media/Space-Routing.png)

借助通连环境的此内置功能，可在共享环境中端到端地测试代码，而无需每个开发人员在其空间中重新创建完整的服务堆栈。 请注意，此路由需要在应用代码中转发传播标头，如本指南上一步所示。

## <a name="test-code-running-in-the-scott-space"></a>测试在 `scott` 空间中运行的代码
若要结合 `webfrontend` 测试 `mywebapi` 的新版本，请打开浏览器并转到 `webfrontend` 的公共访问点 URL（例如， https://webfrontend-teamenv.vsce.io)），然后转到“关于”页。 应看到原始消息“Hello from webfrontend and Hello from mywebapi”。

现在，将“scott-”部分添加到 URL 中，使其形式如 https://scott-webfrontend-teamenv.vsce.io 所示，然后刷新浏览器。 应命中在 `mywebapi` 项目中设置的断点。 单击 F5 继续，现在应在浏览器中看到新消息“Hello from webfrontend and mywebapi now says something new”。 这是因为 `mywebapi` 中更新代码的路径正在 `scott` 空间中运行。

> [!div class="nextstepaction"]
> [摘要](get-started-netcore-visualstudio-07.md)