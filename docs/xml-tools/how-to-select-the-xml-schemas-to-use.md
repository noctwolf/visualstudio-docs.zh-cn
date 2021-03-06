---
title: 如何：选择要使用的 XML 架构
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d6fda3ef-d465-4788-8514-2f2d528d658c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 41f830214b20df24587cf902e6b180e8a43a8cd3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63007384"
---
# <a name="how-to-select-the-xml-schemas-to-use"></a>如何：选择要使用的 XML 架构

XML 编辑器提供的架构缓存位于 *%VSInstallDir%\xml\Schemas*目录。 架构缓存中包括用于智能感知和 XML 文档验证的常见 XML 架构。

使用**架构**文档属性选择一个或多个 XML 架构定义语言 (XSD) 架构。 您可以选择从架构缓存或其他位置的架构。

指定的架构保存在 （隐藏） 解决方案用户选项文件 (。*suo*)，以及所有其他 XML 文档属性。 因此，您无需重新输入这些值的下次打开该解决方案。

> [!NOTE]
> 编辑器可以使用内联架构或引用的架构进行验证`xsd:schemaLocation`属性。 有关详细信息，请参阅[XML 文档验证](../xml-tools/xml-document-validation.md)。

## <a name="to-select-an-xml-schema-from-the-schema-cache"></a>若要从架构缓存中选择 XML 架构

1. 在“XML 编辑器”中打开文件。

2. 在文档属性窗口中，单击**架构**字段。 浏览按钮 （...） 时出现，请单击它。

   ![XML 文件的架构属性](media/properties-schemas.png)

   [XML 架构对话框的](xml-schemas-dialog-box.md)随即打开。 对话框中列出了与所有架构。*xsd*架构缓存中的扩展 (包括架构中引用*catalog.xml*文件)，并且还将在当前解决方案中，打开在 Visual Studio 中，引用中的任何架构`xsd:schemaLocation`属性，或在引用**架构**属性。

3. 通过执行下列操作之一选择用于验证的架构：

   - 选择架构中列出**XML 架构**对话框中，单击**使用**列，，然后选择**使用此架构**。

     或

   - 选择多个架构中列出**XML 架构**对话框中，然后右键单击并选择**使用此架构**。

4. 选择 **“确定”**。

   所选架构的列表复制回**架构**文档属性。

## <a name="to-add-an-xml-schema-to-the-schema-cache"></a>若要将 XML 架构添加到架构缓存

1. 在文档属性窗口中，单击上按钮**架构**字段。

2. 单击 **添加**。

   **打开 XSD 架构**对话框随即打开。

3. 浏览并选择要添加到架构缓存的架构。

4. 单击“打开”。

   这些架构添加到架构缓存并**使用**列的值设置为**使用此架构**。

## <a name="to-delete-an-xml-schema-from-the-schema-cache"></a>若要从架构缓存中删除 XML 架构

1. 在文档属性窗口中，单击上按钮**架构**字段。

2. 选择要删除，然后单击的架构**删除**。

   此架构即会从内存中的架构缓存中移除，但不会从文件系统中移除。

   > [!NOTE]
   > 如果您仍然可以对通过架构的引用`schemaLocation`属性，或者有匹配`targetNamespace`然后**删除**将无法在这种情况下，由于自动关联。 在这种情况下建议将标记作为架构**不使用所选的架构**中**使用**列。

## <a name="see-also"></a>请参阅

- [架构缓存](../xml-tools/schema-cache.md)
- [XML 架构对话框](../xml-tools/xml-schemas-dialog-box.md)
- [XML 编辑器](../xml-tools/xml-editor.md)