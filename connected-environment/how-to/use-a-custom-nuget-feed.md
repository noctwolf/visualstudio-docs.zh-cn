---
title: 如何在连接的环境中使用自定义 NuGet 源 | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 03/27/2018
ms.topic: article
description: 在连接的环境中使用自定义 NuGet 源访问和使用 NuGet 包。
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: ghogen
ms.openlocfilehash: 94956e061302281ef232205081346c0aa90eab90
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
#  <a name="use-a-custom-nuget-feed-in-a-connected-environment"></a>在连接的环境中使用自定义 NuGet 源

可利用 NuGet 源在项目中轻松纳入包源。 连接的环境需要能够访问此源，从而保证依赖项正确安装在 Docker 容器中。

若要设置 NuGet 源：
1. 在 `PackageReference` 节点下的 `*.csproj` 文件中添加[包参考](https://docs.microsoft.com/en-us/nuget/consume-packages/package-references-in-project-files)。

   ```xml
   <ItemGroup>
       <!-- ... -->
       <PackageReference Include="Contoso.Utility.UsefulStuff" Version="3.6.0" />
       <!-- ... -->
   </ItemGroup>
   ```

2. 在项目文件夹中创建 [NuGet.Config](https://docs.microsoft.com/en-us/nuget/reference/nuget-config-file)。
     * 使用 `packageSources` 部分引用 NuGet 源位置。 重要说明：NuGet 源必须可公开访问。
     * 使用 `packageSourceCredentials` 部分配置用户名和密码凭据。 

   ```xml
   <packageSources>
       <add key="Contoso" value="https://contoso.com/packages/" />
   </packageSources>

   <packageSourceCredentials>
       <Contoso>
           <add key="Username" value="user@contoso.com" />
           <add key="ClearTextPassword" value="33f!!lloppa" />
       </Contoso>
   </packageSourceCredentials>
   ```

3. 如果使用源代码管理功能集：
    - 在 `.gitignore` 文件中引用 `NuGet.Config`，避免误将将凭据提交到源存储库。
    - 打开项目中的 `vsce.yaml` 文件并找到 `build` 部分，然后插入以下片段，确保 `NuGet.Config` 文件将同步到 Azure，这样才能在容器映像生成过程中使用此文件。 （默认情况下，连接的环境不同步符合 `.gitignore` 和 `.dockerignore` 规则的文件。）

        ```yaml
        build:
        useGitIgnore: true
        ignore:
        - “!NuGet.Config”
        ```


## <a name="next-steps"></a>后续步骤

完成上述步骤后，下一次运行 `vsce up`（或在 VSCode 或 Visual Studio 中点击 `F5`）时，连接的环境会将 `NuGet.Config` 文件同步到 Azure，随后 `dotnet restore` 将使用此文件在容器中安装包依赖项。

