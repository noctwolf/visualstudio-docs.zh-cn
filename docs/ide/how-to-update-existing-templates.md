---
title: 更新现有项目项模板
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: db5b9c3f601ae11b704e54ae2ebcd58f10c4c724
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53835823"
---
# <a name="how-to-update-existing-templates"></a>如何：更新现有模板

创建模板并将文件压缩为一个 .zip 文件后，可能想要修改该模板。 可以通过以下两种方式完成此操作，即手动更改模板中的文件，或者从基于该模板的项目中导出新模板。

## <a name="using-the-export-template-wizard-to-update-an-existing-project-template"></a>使用“导出模板向导”更新现有项目模板

Visual Studio 提供了“导出模板向导”，该向导可用于更新现有模板：

1. 通过选择“文件” > “新建” > “项目”来打开“新建项目”对话框。

1. 选择要更新的模板，输入项目的名称和位置，然后选择“确定”。

1. 修改 Visual Studio 中的项目。

1. 在“项目”菜单上，选择“导出模板”。

    “导出模板向导”随即打开。

1. 按照向导中的提示将模板以 .zip 文件导出。

1. （可选）要将模板添加到“新建项目”对话框，请将 .zip 文件放在以下目录中：%USERPROFILE%\Documents\Visual Studio \<version\>\Templates\ProjectTemplates。 如果未在“导出模板向导”中选择“自动将模板导入 Visual Studio”选项，则需执行此步骤。

1. 删除旧的模板 .zip 文件。

## <a name="manually-update-an-existing-template"></a>手动更新现有模板

可通过修改压缩的 .zip 文件中的文件来更新现有模板，而无需使用“导出模板向导”。

### <a name="to-manually-update-an-existing-template"></a>手动更新现有模板

1. 找到包含模板的 .zip 文件。 用户项目模板通常位于 %USERPROFILE%\Documents\Visual Studio \<version\>\Templates\ProjectTemplates。

1. 解压缩 .zip 文件。

1. 修改或删除当前的模板文件，或向该模板添加新文件。

1. 打开、修改并保存 .vstemplate XML 文件，以处理已更新的行为或新文件。

    有关 .vstemplate 架构的详细信息，请参阅 [Visual Studio 模板架构引用（扩展性）](../extensibility/visual-studio-template-schema-reference.md)。 有关可在源文件中进行参数化的内容的详细信息，请参阅[模板参数](../ide/template-parameters.md)。

1. 选择模板中的文件，然后通过右键单击或从上下文菜单中选择“发送至” > “压缩的文件夹（zip 格式）”。

    所选的文件将压缩到一个 .zip 文件中。

1. 将新 .zip 文件放在旧 .zip 文件的同一目录中。

1. 删除解压缩的模板文件和旧的 .zip 模板文件。

## <a name="see-also"></a>请参阅

- [自定义模板](../ide/customizing-project-and-item-templates.md)
- [创建项目和项模板](../ide/creating-project-and-item-templates.md)
- [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)
- [模板参数](../ide/template-parameters.md)