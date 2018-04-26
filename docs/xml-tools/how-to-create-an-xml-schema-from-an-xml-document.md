---
title: 如何：从 XML 文档创建 XML 架构
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6c6980eda6e0f710821cf24cbf3ace01ffa98b54
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>如何：从 XML 文档创建 XML 架构

使用“XML 编辑器”可以从 XML 文档创建 XML 架构定义语言 (XSD) 架构。 XML 实例文档通过以下方式确定如何生成架构：

-   如果 XML 文档没有关联的架构或文档类型定义 (DTD)，将使用 XML 文档中的数据推断新的 XML 架构。

-   如果 XML 文档包含关联的 DTD，外部 DTD 和内部子集将转换为相应的 XML 架构。

-   如果 XML 文档包含内联的 XML 数据简化 (XDR) 架构，XDR 架构将转换为相应的 XML 架构。

然后，将使用创建的架构为 XML 文档提供智能感知。

有关架构推断引擎的详细信息，请参阅[推断 XML 架构](/dotnet/standard/data/xml/inferring-an-xml-schema)。

## <a name="to-create-an-xml-schema"></a>创建 XML 架构

1.  将 XML 实例文档加载到“XML 编辑器”中。

2.  单击**Create Schema**按钮从**工具栏**。

     将为 XML 实例文档中发现的每个命名空间创建并打开一个 XML 架构文档。 每个架构作为临时的杂项文件打开。

     架构可以保存到磁盘中、添加到项目中或丢弃。

    > [!NOTE]
    >  **Create Schema**命令也是可从 XML 编辑器和下的快捷菜单**XML**菜单。

## <a name="see-also"></a>请参阅

- [XML 编辑器](../xml-tools/xml-editor.md)