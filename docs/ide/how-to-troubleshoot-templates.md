---
title: 对 Visual Studio 项目模板和项模板加载进行故障排除 | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- templates [Visual Studio], troubleshooting
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: f7e952f8eb445787a2a574ae3431ba6ad8728248
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-troubleshoot-templates"></a>如何：对模板进行故障排除

如果模板在开发环境中无法加载，可以采用以下几种方法找出问题。

## <a name="validate-the-vstemplate-file"></a>验证 .vstemplate 文件

如果模板中的 .vstemplate 文件未遵循 Visual Studio 模板架构，则“新建项目”对话框中可能不会显示该模板。

### <a name="to-validate-the-vstemplate-file"></a>验证 .vstemplate 文件

1. 找到包含模板的 .zip 文件。

1. 解压缩 .zip 文件。

1. 在 Visual Studio 的“文件”菜单上，选择“打开” > “文件”。

1. 选择模板的 .vstemplate 文件，然后选择“打开”。

1. 验证 .vstemplate 文件的 XML 是否遵循模板架构。 有关 .vstemplate 架构的详细信息，请参阅[模板架构参考](../extensibility/visual-studio-template-schema-reference.md)。

    > [!NOTE]
    > 要在创作 .vstemplate 文件时获得 IntelliSense 支持，请将 `xmlns` 特性添加到 `VSTemplate` 元素，并为其赋值 http://schemas.microsoft.com/developer/vstemplate/2005。

1. 保存并关闭 .vstemplate 文件。

1. 选择模板中包含的文件，右键单击，然后选择“发送至” > “压缩的文件夹（zip 格式）”。 所选的文件将压缩到一个 .zip 文件中。

1. 将新的 .zip 文件与旧的 .zip 文件放在同一目录中。

1. 删除解压缩的模板文件和旧的 .zip 模板文件。

## <a name="enable-diagnostic-logging"></a>启用诊断记录

可按照[模板发现疑难解答（扩展性）](../extensibility/troubleshooting-template-discovery.md)中的步骤启用模板发现的诊断日志记录。

## <a name="see-also"></a>请参阅

[模板发现疑难解答（扩展性）](../extensibility/troubleshooting-template-discovery.md)  
[自定义模板](../ide/customizing-project-and-item-templates.md)  
[创建项目和项模板](../ide/creating-project-and-item-templates.md)  
[模板架构引用](../extensibility/visual-studio-template-schema-reference.md)