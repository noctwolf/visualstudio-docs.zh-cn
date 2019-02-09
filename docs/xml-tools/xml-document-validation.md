---
title: 在 XML 编辑器中的 XML 文档验证
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: abb353bd-6c4a-4978-b03b-a8c245bbfb55
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 74c8f327f17e6d2e05d0748195cb139f3a05a6f4
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55931190"
---
# <a name="xml-document-validation"></a>XML 文档验证

“XML 编辑器”检查 XML 1.0 语法，还会在您键入时执行数据验证。 编辑器可以使用文档类型定义 (DTD) 或架构进行验证。 红色的波浪形下划线突出显示任何 XML 1.0 格式正确的错误。 蓝色的波浪形下划线根据 DTD 或架构验证显示语义错误。 每个错误在错误列表中有关联的条目。 将鼠标光标暂时停留在波浪形下划线上，也可以查看错误消息。

 将已编译架构的 `targetNamespace` 与元素的 xmlns 声明进行匹配，可以找到验证中使用的架构。 已编译架构从下列位置之一加载（按优先级顺序列出）：

-   在指定的文件名称**架构**的文档字段**属性**窗口。

-   内联架构或 DTD。

-   外部 DTD 或 `xsd:schemaLocation` 和 `xsd:noNamespaceSchemaLocation` 属性

-   “x-schema”XDR 架构命名空间 URI。

如果架构具有非空目标命名空间，在下列附加位置也可以找到架构：

-   包含架构的另一个编辑器窗口。

-   当前解决方案中的架构。

-   架构缓存目录中的架构。

## <a name="xslt-files"></a>XSLT 文件
 编辑 XSLT 文件时*xslt.xsd*使用架构缓存中的文件进行验证。 验证错误以蓝色的波浪形下划线显示。 XSLT 编译器中的错误显示为红色的波浪形下划线。

## <a name="xml-schema-xsd-files"></a>XML 架构 (XSD) 文件
 编辑 XML 架构文件时*xsdschema.xsd*使用架构缓存中的文件进行验证。 验证错误以蓝色的波浪形下划线显示。 任何编译错误也会显示为红色的波浪形下划线。

## <a name="see-also"></a>请参阅

- [XML 编辑器](../xml-tools/xml-editor.md)