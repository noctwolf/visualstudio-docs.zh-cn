---
title: T4 文本模板的 API 参考
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: bef33f10446df92ae8424b23aa17695748222808
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="api-reference-for-t4-text-templates"></a>T4 文本模板的 API 参考

文本模板化 API 可以调用和自定义的转换[文本模板](../modeling/code-generation-and-t4-text-templates.md)。

## <a name="namespaces"></a>命名空间

|命名空间|目标|
|---------------|-------------|
|<xref:Microsoft.VisualStudio.TextTemplating>|包含文本模板转换功能的类。 文本模板转换引擎集成到 Visual Studio 中，并将文本模板文件转换为生成的文本输出文件。|
|<xref:Microsoft.VisualStudio.TextTemplating.Modeling>|提供与 UML 模型和域特定语言，例如访问相关的转换功能的文本[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ModelBus。|
|<xref:Microsoft.VisualStudio.TextTemplating.VSHost>|提供对中的文本模板化服务的访问[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。|