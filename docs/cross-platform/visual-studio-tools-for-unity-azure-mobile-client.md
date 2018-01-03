---
title: "Visual Studio Tools for Unity Azure 演练移动客户端 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5A8762A1-D843-4FD8-A89B-E5E489ECA03D
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 451b4f1f2580a55077bf3fc6a9ad3f16a2afaf0f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="implement-the-azure-mobileserviceclient"></a>实现 Azure MobileServiceClient

Azure 移动客户端 SDK 的核心是 <a href="https://msdn.microsoft.com/en-us/library/azure/microsoft.windowsazure.mobileservices.mobileserviceclient(v=azure.10).aspx">MobileServiceClient</a>，后者用于访问移动应用后端。

## <a name="locate-the-url-of-the-mobile-app-backend"></a>找到移动应用后端的 URL

`MobileServiceClient` 构造函数将移动应用 URL 作为参数，因此在执行后续操作前，先找到该 URL。

1. 在 Azure 门户中，单击“应用程序服务”按钮。

    ![单击“应用程序服务”](media/vstu_azure-implement-azure-mobileserviceclient-image1.png)

2. 单击移动应用的相应条目。

    ![单击移动应用](media/vstu_azure-implement-azure-mobileserviceclient-image2.png)

3. 复制移动应用后端的 URL。

    ![复制 URL](media/vstu_azure-implement-azure-mobileserviceclient-image3.png)

## <a name="create-the-mobileserviceclient-singleton"></a>创建 MobileServiceClient 单一实例

`MobileServiceClient` 只能有一个实例，因此本演练使用单一实例模式的变体。

1. 在 Unity 项目的 **Assets/Scripts** 目录内，创建一个名为 **AzureMobileServiceClient** 的新 C# 脚本。

2. 打开 `AzureMobileServiceClient` 脚本并删除任何现有的模板代码，包括 using 语句和类声明。

3. 添加以下代码：

  ```csharp
  using Microsoft.WindowsAzure.MobileServices;

  public static class AzureMobileServiceClient
  {
      private const bool ignoreTls = true;
      private const string backendUrl = "MOBILE_APP_URL";
      private static MobileServiceClient client;

      public static MobileServiceClient Client
      {
          get
          {
              if (client == null)
              {
                  client = new MobileServiceClient(backendUrl);
              }

              return client;
          }
      }
  }
  ```

  > [!NOTE]
  > 如果 IntelliSense 无法识别 Microsoft.WindowsAzure 命名空间，请确保已完成[准备开发环境]()部分中的所有步骤。

4. 在前面的代码中，将 `MOBILE_APP_URL` 替换为移动应用后端的 URL。

## <a name="next-step"></a>下一步

* [更新 Unity Mono 安全存储](visual-studio-tools-for-unity-azure-security.md)
