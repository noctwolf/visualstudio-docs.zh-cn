---
title: 如何在通连环境中使用 kubectl | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 03/12/2018
ms.topic: article
ms.technology: vsce-kubernetes
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: ghogen
ms.openlocfilehash: 46c69f80e58a4265aa5e4320e731c3ad241a8116
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="use-kubectl-with-a-connected-environment"></a>在通连环境中使用 `kubectl`

可以访问通连环境中的 Kubernetes 群集，并使用现有的 Kubernetes 工具（例如 `kubectl`）。

运行 `vsce env create` 或 `vsce env select` 会自动添加 `kubectl` 配置上下文，因此 kubectl 应该已连接到 VSCE Kubernetes 群集。 示例：
- 确认当前上下文：`kubectl config current-context`
- 列出所有可用内容：`kubectl config get-contexts`。 由 VSCE 创建的 kubernetes 群集将被命名为例如“vsce-<guid>”。
- 更改上下文：`kubectl config use-context <context-name>`
- 查看 Kubernetes 仪表板：运行 `kubectl proxy`，然后打开浏览器并转到该命令发出的地址（在 URL 末尾追加 `/ui` 以导航到 Kubernetes 仪表板）。
- 列出名为“mainline”的默认 VSCE 空间中正在运行的服务：`kubectl get services --namespace=mainline`

