---
title: 如何：选择要使用的 XML 架构
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: d6fda3ef-d465-4788-8514-2f2d528d658c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d835a8592108b549a109f7bb7e128a8ae5b01611
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2018
ms.locfileid: "34549098"
---
# <a name="how-to-select-the-xml-schemas-to-use"></a>如何： 选择要使用的 XML 架构

XML 编辑器提供的架构缓存位于 *%InstallDir%\Xml\Schemas*目录。 架构缓存中包括用于智能感知和 XML 文档验证的常见 XML 架构。

**架构**文档属性用于选择一个或多个 XML 架构定义语言 (XSD) 架构使用。 使用该属性可以从架构缓存中选择架构，也可以指定不在缓存中的架构。

指定的架构保存在隐藏解决方案用户选项文件 (。*suo*)，以及所有其他 XML 文档属性。 因此，下次打开该解决方案时，不必重新输入这些值。

> [!NOTE]
> 编辑器可以使用内联架构或 `xsd:schemaLocation` 属性引用的架构来进行验证。 有关详细信息，请参阅[XML 文档验证](../xml-tools/xml-document-validation.md)。

## <a name="to-select-an-xml-schema-from-the-schema-cache"></a>若要从架构缓存中选择 XML 架构

1.  在“XML 编辑器”中打开文件。

2.  在文档属性窗口中，单击按钮上**架构**字段。

     **XML 架构**对话框随即显示。 该对话框列出包含的所有架构。*xsd*架构缓存中的扩展 (包括架构中引用*catalog.xml*文件)，并且还将在当前解决方案中，打开在 Visual Studio 中，引用中的任何架构`xsd:schemaLocation`属性，或在引用**架构**属性。

3.  通过执行下列操作之一选择用于验证的架构：

    -   选择一个列出中的架构**XML 架构**对话框中，单击**使用**列，，然后选择**使用此架构**。

     -或-

    -   选择多个架构中列出**XML 架构**对话框，右键单击并选择**使用此架构**。

4.  单击 **“确定”**。

     所选架构的列表复制回**架构**文档属性。

## <a name="to-add-an-xml-schema-to-the-schema-cache"></a>将 XML 架构添加到架构缓存

1.  在文档属性窗口中，单击按钮上**架构**字段。

2.  单击 **添加**。

     这将打开**打开 XSD 架构**对话框。

3.  浏览并选择要添加到架构缓存的架构。

4.  单击**打开**。

     添加到架构的架构缓存，并且**使用**列值设置为**使用此架构**。

## <a name="to-delete-an-xml-schema-from-the-schema-cache"></a>若要从架构缓存中删除 XML 架构

1.  在文档属性窗口中，单击按钮上**架构**字段。

2.  选择要删除，然后单击的架构**删除**。

     此架构即会从内存中的架构缓存中移除，但不会从文件系统中移除。

    > [!NOTE]
    > 如果您仍然必须对通过架构的引用`schemaLocation`属性，或者有匹配`targetNamespace`然后**删除**中由于自动关联这种情况下将不工作。 在这种情况下建议你将为此架构标记**不使用所选的架构**中**使用**列。

## <a name="see-also"></a>请参阅

- [架构缓存](../xml-tools/schema-cache.md)
- [XML 架构对话框](../xml-tools/xml-schemas-dialog-box.md)
- [XML 编辑器](../xml-tools/xml-editor.md)