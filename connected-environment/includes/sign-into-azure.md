---
ms.topic: include
ms.openlocfilehash: 502bd8d206b43fc219c850ab870db35e6c3af1c0
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
## <a name="sign-in-to-azure"></a>登录 Azure
需要登录 Azure 才能创建开发环境。 在终端窗口中键入以下命令：
```cmd
az login
```

> [!Note]
> 如果没有 Azure 订阅，可以创建[免费帐户](https://azure.microsoft.com/free)。

### <a name="if-you-have-multiple-azure-subscriptions"></a>如果有多个 Azure 订阅...
则可以运行以下命令查看订阅： 
```cmd
az account list
```
在 JSON 输出中找到具有 `isDefault: true` 的订阅。
如果这不是要使用的订阅，则可以更改默认订阅：
```cmd
az account set --subscription <subscription ID>
```
