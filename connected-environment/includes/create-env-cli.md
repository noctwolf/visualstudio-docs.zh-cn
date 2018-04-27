---
ms.topic: include
ms.openlocfilehash: 97f9885780c9f697cfc6a58b78054761fdcd725d
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
## <a name="create-a-kubernetes-development-environment-in-azure"></a>在 Azure 中创建 Kubernetes 开发环境
借助通连环境，可创建基于 Kubernetes 的环境，这些开发环境由 Azure 完全托管，并针对开发进行了优化。 该命令在 `eastus` 中创建名为 `mydevenvironment` 的环境。
```cmd
vsce env create --name mydevenvironment --location eastus
```

支持的位置：`eastus`、`westeurope`

> [!Note]
> 执行该命令大约需要 6 分钟。 无需等待命令完成，可继续执行本指南中的操作。
