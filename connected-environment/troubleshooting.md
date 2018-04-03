---
title: 疑难解答 | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: article
ms.technology: vsce-kubernetes
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: ghogen
ms.openlocfilehash: 0f35e31e3f3a109e65565592b56b6dc4177dd7c0
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="troubleshooting-guide"></a>故障排除指南

## <a name="error-upstream-connect-error-or-disconnectreset-before-headers"></a>错误“上游连接错误或在标头之前断开连接/重置”
尝试访问服务时可能会看到此错误。 例如，在浏览器中访问服务的 URL 时。 

**原因：**容器端口不可用。 以下是常见原因： 
* 容器仍在生成和部署过程中。 如果运行 `vsce up` 或启动调试程序，然后在部署成功之前尝试访问容器，则可能会出现这种情况。
* Dockerfile、Helm Chart 和任何打开端口的服务器代码中的端口配置不一致。

**请尝试：**
1. 如果容器处于生成/部署过程中，请等待 2-3 秒，然后再次尝试访问该服务。 
1. 检查端口配置。 以下所有资产中的指定端口号应完全相同：
    * **Dockerfile：**由 `EXPOSE` 指令指定。
    * **[Helm chart](https://docs.helm.sh)：**由服务的 `externalPort` 和 `internalPort` 值（通常位于 `values.yml` 文件中）指定。
    * 任何在 Node.js 等应用程序代码中打开的端口：`var server = app.listen(80, function () {...}`


## <a name="config-file-not-found"></a>找不到配置文件
运行 `vsce up` 时遇到以下错误：`Config file not found: .../vsce.yaml`

**原因：**需从要运行的代码的根目录运行 `vsce up`，并且需初始化代码文件夹，以便在通连环境中运行。

**请尝试：**
1. 将当前目录更改为包含服务代码的根文件夹。 
1. 如果代码文件夹中没有 vsce.yaml 文件，请运行 `vsce init`，生成 Docker、Kubernetes 和 VSCE 资产。

## <a name="error-the-pipe-program-vsce-exited-unexpectedly-with-code-126"></a>错误：“管道程序 'vsce' 意外退出，错误代码 126。”
启动 VS Code 调试程序有时可能会导致此错误。 这是一个 bug。

**请尝试：**
1. 关闭并重新打开 VS Code。
2. 再次点击 F5。


## <a name="debugging-error-configured-debug-type-coreclr-is-not-supported"></a>调试错误“不支持配置的调试类型 'coreclr'”
运行 VS Code 调试程序时报告错误：`Configured debug type 'coreclr' is not supported.`

**原因：**开发计算机上未安装适用于通连环境的 VS Code 扩展。

**请尝试：**安装[适用于通连环境的 VS Code 扩展](get-started-netcore-01.md#get-kubernetes-debugging-for-vs-code)。


## <a name="the-azure-portal-doesnt-show-connected-environment-instances"></a>Azure 门户不显示通连环境实例

**原因：**通连环境的 Azure 门户体验尚未准备就绪，无法预览。


## <a name="the-type-or-namespace-name-mylibrary-could-not-be-found"></a>找不到类型或命名空间名称“MyLibrary”

**原因：**默认情况下，生成上下文为项目/服务级别，因此找不到正在使用的库项目。

**请尝试：**需要完成的操作：
1. 修改 vsce.yaml 文件，将生成上下文设置为解决方案级别。
2. 修改 Dockerfile 和 Dockerfile.develop 文件，相对于新的生成上下文正确引用 csproj 文件。
3. 在 .sln 文件旁放置一个 .dockerignore 文件并根据需要进行修改。

可在 https://github.com/sgreenmsft/buildcontextsample 找到示例

## <a name="microsoftconnectedenvironmentregisteraction-authorization-error-when-creating-an-environment"></a>创建环境时出现“Microsoft.ConnectedEnvironment/register/action”授权错误
在管理环境，并且使用没有“所有者”或“参与者”访问权限的 Azure 订阅时，可能会看到以下错误。
`The client '<User email/Id>' with object id '<Guid>' does not have authorization to perform action 'Microsoft.ConnectedEnvironment/register/action' over scope '/subscriptions/<Subscription Id>'.`

**原因：**所选 Azure 订阅尚未注册 Microsoft.ConnectedEnvironment 命名空间。

**请尝试：**具有 Azure 订阅的“所有者”或“参与者”访问权限的用户可运行以下 Azure CLI 命令，手动注册 Microsoft.ConnectedEnvironment 命名空间：

```cmd
az provider register --namespace Microsoft.ConnectedEnvironment
```

## <a name="vsce-doesnt-seem-to-use-my-existing-dockerfile-to-build-a-container"></a>VSCE 似乎没有使用现有 Dockerfile 来生成容器 

**原因：**可以将 VSCE 配置为指向项目中的特定 Dockerfile。 如果 VSCE 没有使用预期的 Dockerfile 来生成容器，可能需要显示通知 VSCE Dockerfile 所在位置。 

**请尝试：**在项目中打开 VSCE 生成的 `vsce.yaml` 文件。 使用 `configurations->develop->build->dockerfile` 指令指向要使用的 Dockerfile：

```
...
configurations:
  develop:
    build:
      dockerfile: Dockerfile.develop
```