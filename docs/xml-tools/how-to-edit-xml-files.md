---
title: 如何：编辑 XML 文件
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 07fa3ecf-6345-4d30-9d85-d5ef5b083319
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b25eebad9efc70e4fda45131e232983e81961625
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62840364"
---
# <a name="how-to-edit-xml-files"></a>如何：编辑 XML 文件

XML 编辑器是 XML 文件的新编辑器。 该编辑器可以用于独立的 XML 文件，也可以用于与 Visual Studio 项目关联的文件。 XML 编辑器是与以下文件扩展名相关联： *.config*， *.dtd*， *.xml*， *.xsd*， *.xdr*， *.xsl*， *.xslt*，并且 *.vssettings*。 XML 编辑器也是与任何其他文件类型关联的具有注册任何特定编辑器并且包含 XML 或 DTD 内容。

> [!NOTE]
> XHTML 文档由“HTML 编辑器”处理。

若要编辑的 XML 文件，请双击你想要编辑的文件。

## <a name="add-a-new-xml-file-to-a-project"></a>向项目添加新的 XML 文件

1. 从**项目**菜单中，选择**添加新项**。

2. 选择**XML 文件**从**模板**窗格。

3. 输入中的文件名**名称**字段并按**添加**。

   XML 文件添加到项目，并在 XML 编辑器中打开。 该文件包含默认的 XML 声明 `<?xml version="1.0" encoding="utf-8" ?>`。

## <a name="add-an-existing-xml-file-to-a-project"></a>向项目添加现有的 XML 文件

1. 从**项目**菜单中，选择**添加现有项**。

   **添加现有项**对话框随即出现。

2. 选择 XML 文件，然后按**添加**。

## <a name="create-a-new-xml-or-xslt-file"></a>创建一个新的 XML 或 XSLT 文件

1. 从**文件**菜单中，选择**新建**。

   **新的文件**对话框随即出现。

2. 选择**XML 文件**若要创建新的 XML 文件; 或者，选择**XSLT 文件**若要创建新的 XSLT 样式表。

3. 单击“打开”。

## <a name="create-an-empty-project-for-xml-files"></a>创建用于 XML 文件的空项目

::: moniker range="vs-2017"

1. 从**文件**菜单中，选择**新建** > **项目**。

   此时将出现“新建项目”对话框。

2. 选择您的选择，选择的代码语言**空项目**。

3. 单击 **“确定”**。

::: moniker-end

::: moniker range=">=vs-2019"

1. 从**文件**菜单中，选择**新建** > **项目**。

2. 输入**空项目**在模板搜索框中，选择**空项目 (.NET Framework)** 模板，，然后单击**下一步**。

3. 单击 **“创建”**。

::: moniker-end

4. 将 XML 文件添加到项目中。

   XML 编辑器找到添加到此项目的架构，并将其用于验证和任何 XML、 架构或编辑此项目处于打开状态时的 XSLT 文件中的 IntelliSense。

## <a name="see-also"></a>请参阅

- [XML 编辑器](../xml-tools/xml-editor.md)
- [XML 文档属性，属性窗口](../xml-tools/xml-document-properties-properties-window.md)
- [如何：从 XML 文档创建 XML 架构](../xml-tools/how-to-create-an-xml-schema-from-an-xml-document.md)