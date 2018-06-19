---
title: Azure Functions 简介
description: 在 Visual Studio for Mac 中使用 Azure Functions。
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 25CD47A4-5B32-4734-8EF3-E24A02AABF29
ms.openlocfilehash: 5d787efbd09ad7f2d4a1f5f72b8f1493d8c6c587
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33870408"
---
# <a name="introduction-to-azure-functions"></a>Azure Functions 简介

Azure functions 是一种在云中创建和运行事件驱动的代码片段（函数）的方法，无需显式预配或管理基础结构。 有关 Azure Functions 的详细信息，请参阅 [Azure Functions 文档](https://docs.microsoft.com/azure/azure-functions/)。

## <a name="requirements"></a>惠?

Azure Function 工具包含在 Visual Studio for Mac 7.5 中。

若要创建和部署函数，还需要 Azure 订阅，可从 [https://azure.com/free](https://azure.com/free) 免费获取。

## <a name="creating-your-first-azure-functions-project"></a>创建第一个 Azure Functions 项目

1. 在 Visual Studio for Mac 中，选择“文件”>“新建解决方案…” 
2. 从“新建项目”对话框，选择“云”>“常规”下的 Azure Functions 模板并单击“下一步”：

    ![显示 Azure functions 选项的“新建项目”对话框](media/azure-functions-image1.png)

3. 输入项目名称并选择“创建”。

Visual Studio for Mac 使用包含的默认 HttpTrigger 函数创建 .NET Standard 项目。 它还包括对各种 AzureWebJobs 包以及 Newtonsoft.Json 包的 NuGet 引用。

![显示模板中的全新 Azure 函数的 Visual Studio for Mac 编辑器](media/azure-functions-newproj.png)

新项目包含以下文件：

* **HttpTrigger.cs** - 该类包含 HTTP 触发的函数的 boilerplate 代码。 其中包含一个带有函数名称的 FunctionName 属性和一个触发器属性（HttpTrigger，指定函数由 HTTP 请求触发）。 有关函数方法的详细信息，请参阅 [Azure Functions C# 开发人员参考](https://docs.microsoft.com/azure/azure-functions/functions-dotnet-class-library)一文。
* **host.json** - 该文件介绍 Functions 主机的全局配置选项。 有关示例文件和该文件的可用设置的信息，请参阅 [Azure Functions 的 host.json 引用](https://docs.microsoft.com/azure/azure-functions/functions-host-json)。
* **local.settings.json** - 该文件包含用于在本地运行函数的所有设置。 这些设置由 Azure Functions 核心工具使用。 有关详细信息，请参阅“Azure Functions 核心工具”一文中的[本地设置文件](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local#local-settings-file)。

在 Visual Studio for Mac 中创建新的 Azure Functions 项目后，可以从本地计算机测试默认 HTTP 触发的函数。

<!--
## Create an Azure storage account

[Describe why this step is necessary and what it does]

1. Log on to your account at [https://portal.azure.com](https://portal.azure.com).
2. Under the **Favorites** section, located on the left of the screen, select **Storage Accounts**:
    ![]()
3. Select **Add** to create a new storage account:
    ![]()
4. Enter a globally unique name for the **Name** and reuse it for the **Resource group**. You can keep all the other items as their default.
    ![]()
5. Click **Create**. It might take a few minutes to create the storage account. You'll get a notification once it has been successfully created.
6. Select the **Go to resource** button from the notification:
    ![]()
-->

## <a name="testing-the-function-locally"></a>在本地测试函数

使用 Visual Studio for Mac 中的 Azure Functions，可以在本地开发计算机上测试和调试函数。

1. 若要在本地测试函数，请按 Visual Studio for Mac 中的“运行”按钮：

    ![在 Visual Studio for Mac 中启动调试按钮](media/azure-functions-run.png)

1. 运行项目可启动 Azure Function 上的本地调试并打开一个新的终端窗口，如下图中所示： 

    ![显示函数输出的终端窗口](media/azure-functions-terminal.png) 

    从输出中复制 URL。

3. 将 HTTP 请求的 URL 粘贴到浏览器的地址栏。 将查询字符串 `?name=<yourname>` 添加到 URL 的末尾并执行请求。 下图显示了浏览器中由函数返回的本地 GET 请求的响应：

    ![浏览器中的 http 请求](media/azure-functions-httpreq.png)

## <a name="creating-a-new-function"></a>创建新函数

函数模板使用户可以使用最常见的触发器和模板快速创建新函数。 创建新的 Azure Functions 项目后，它自动包含 HttpTrigger 函数。 若要创建另一种类型的函数，请执行以下操作：

1. 右键单击 HttpTrigger.cs 文件并选择“删除”以将其删除。 从以下警报选择“删除”，以将其从项目中删除：

    ![从项目中删除文件的对话框](media/azure-functions-remove.png)

2. 若要添加新函数，右键单击项目名称并选择“添加”>“添加函数...”：

    ![用于添加新函数的上下文操作](media/azure-functions-addnew.png)

3. 从“新建 Azure 函数”对话框选择所需的函数：

    ![“新建 Azure 函数”对话框](media/azure-functions-newfunction.png)

    以下部分提供 Azure 函数模板列表。

## <a name="available-function-templates"></a>可用的函数模板

- **HTTP** - 使用 HTTP 请求触发代码的执行。 可用于以下 HTTP 触发器的显式模板：
    - Http GET CRUD
    - Http POST CRUD
    - 带有参数的 Http 触发器
    - Http 触发器
- **计时器** - 按照预定义计划执行清除或其他批处理任务。 此模板采用两个字段：Name 和 schedule（一个具有 6 个字段的 CRON 表达式）。 有关详细信息，请参阅[关于时间的 Azure functions 文章](https://docs.microsoft.com/azure/azure-functions/functions-create-scheduled-function)
- **GitHub 触发器** - 对 GitHub 存储库中发生的事件作出响应。 有关详细信息，请参阅[关于 GitHub 的 Azure Functions 文章](https://docs.microsoft.com/azure/azure-functions/functions-create-github-webhook-triggered-function)
    - GitHub 快速注释 - 此函数在其收到一个问题或拉取请求的 GitHub Webhook 时运行并添加注释。
    - GitHub WebHook - 此函数在其收到 GitHub Webhook 请求时运行
- **Blob 触发器** - 在 Azure 存储 Blob 添加到容器时对其进行处理。 除了函数名称，此模板还采用路径和连接属性。 路径属性是触发器将监视的存储帐户中的路径。 连接帐户是包含存储帐户连接字符串的应用设置的名称。 有关详细信息，请参阅 [Azure Functions Blob 存储](https://docs.microsoft.com/azure/azure-functions/functions-create-storage-blob-triggered-function)一文。
- **队列触发器** - 这是在消息到达 Azure Storage 队列时会对消息进行响应的函数。 除函数名称之外，此模板还采用一个路径（将从中读取消息的队列名称）和存储帐户连接（包含存储帐户连接字符串的应用设置名称）。 有关详细信息，请参阅[关于队列存储的 Azure functions 文章](https://docs.microsoft.com/azure/azure-functions/functions-create-storage-queue-triggered-function)。
- **泛型 WebHook** - 这是一个简单函数，每当从支持 Webhook 的任何服务接收请求时，都会运行此函数。 有关详细信息，请参阅[有关泛型 Webhook 的 Azure functions 文章](https://docs.microsoft.com/azure/azure-functions/functions-create-generic-webhook-triggered-function)
- **图像大小调整工具** - 此函数在每次向容器添加 blob 时都会创建已调整大小的图像。 该模板针对触发器、小图像输出和中等图像输出使用路径和连接字符串。
- **SAS 令牌** - 此函数为给定 Azure 存储容器和 blob 名称生成 SAS 令牌。 除了函数名称，此模板还采用路径和连接属性。 路径属性是触发器将监视的存储帐户中的路径。 连接帐户是包含存储帐户连接字符串的应用设置的名称。 还需设置“访问权限”。 授权级别控制函数是否需要 API 密钥以及要使用的密钥；函数使用功能键；管理员使用主密钥。 有关详细信息，请参阅[用于生成 SAS 令牌 的 C# Azure Function](https://azure.microsoft.com/resources/samples/functions-dotnet-sas-token/) 示例。
- **Durable 函数业务流程** – Durable 函数可使用户在无服务器环境中编写有状态函数。 此扩展管理状态、检查点以及为用户重启。 有关详细信息，请参阅关于 [Durable 函数](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)的 Azure functions 指南