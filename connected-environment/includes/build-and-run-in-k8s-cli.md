---
ms.topic: include
ms.openlocfilehash: b10d15b90f7f413d26adf8037c6f52c711a9ed69
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
ms.locfileid: "32030929"
---
## <a name="build-and-run-code-in-kubernetes"></a>在 Kubernetes 中生成并运行代码
我们来运行代码！ 在终端窗口中，从根代码文件夹 webfrontend 运行以下命令：

```cmd
vsce up
```

时刻关注命令的输出，在运行过程中，你会注意到以下情况：
1. 源代码被同步到 Azure 中的开发环境。
1. 容器映像在 Azure 中生成，由代码文件夹中的 Docker 资产指定。
1. 创建了 Kubernetes 对象，该对象使用代码文件夹中 Helm 图表指定的容器映像。
1. 显示了有关容器终结点的信息。 在本例中，我们希望得到公共 HTTPS URL。
1. 假设上述阶段成功完成，应可在容器启动时看到 `stdout`（和 `stderr`）输出。

> [!Note]
> 第一次运行 `up` 命令时，这些步骤需要较长的时间，但后续运行应该会更快。

## <a name="test-the-web-app"></a>测试 Web 应用
扫描控制台输出，获取有关由 `up` 命令创建的公用 URL 的信息。 它的形式如下： 

`Running at public URL: https://<servicename>-<environmentname>.vsce.io` 

在浏览器窗口中打开此 URL，应可看到 Web 应用加载。 在容器执行时，`stdout` 和 `stderr` 输出将流式传输到终端窗口。
