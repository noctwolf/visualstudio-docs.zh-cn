---
title: 在 Visual Studio 中的模板发现疑难解答 |Microsoft Docs
ms.date: 01/02/2018
ms.topic: conceptual
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 39ebb7c49e5a8482ab0b2ef5c3a5257d0237b39c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53836148"
---
# <a name="troubleshooting-template-installation"></a>模板安装故障排除

如果遇到问题，部署项目或项模板，则可以启用诊断日志记录。

1. 创建您的安装 (例如 C:\Program Files (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\EnablePkgDefLogging.pkgdef) Common7\IDE\CommonExtensions 文件夹中的 pkgdef 文件包含以下内容：

    ```
    [$RootKey$\VsTemplate]
    "EnableTemplateDiscoveryLog"=dword:00000001
    ```

1. 打开"开发人员命令提示"你的安装通过在 Windows 搜索中，搜索并运行`devenv /updateConfiguration`。

1. 启动 Visual Studio，并启动新项目和新项对话框，以便初始化两个模板树。 模板日志现在显示在 **%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_[instanceid]\VsTemplateDiagnosticsList.csv** （对应于您的 Visual Studio 实例的安装 ID 的实例 id）。 每个模板树初始化附加到此日志条目。

日志文件包含以下列：

- **FullPathToTemplate**，其中包含以下值：

    - 1 表示基于清单的部署

    - 0 为基于磁盘的部署的

- **TemplateFileName**

- 其他模板属性

> [!NOTE]
> 若要禁用日志记录，请删除该 pkgdef 文件，或更改的值`EnableTemplateDiscoveryLog`到`dword:00000000`，然后运行`devenv /updateConfiguration`试。

## <a name="see-also"></a>请参阅

[创建自定义项目和项模板](creating-custom-project-and-item-templates.md)