---
title: VS Shell 部署
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 816997f971e90ddd27f8e24cdc1857559e04ff70
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="vs-shell-deployment"></a>VS Shell 部署

独立的 shell，可以确定哪些 Visual Studio 需要与你的域特定语言和该解决方案的显示方式进行交互的功能。 有关 Visual Studio 独立 shell 的详细信息，请参阅[自定义独立 Shell](../extensibility/customizing-the-isolated-shell.md)。

## <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>若要将 Visual Studio Shell 设置为部署目标

1.  在**DslPackage**项目中，打开**source.extension.tt**。

2.  下`<SupportedProducts>`插入：

    ```
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>
    ```

     替换*MyIsolatedShell*与独立的 shell 包的名称。