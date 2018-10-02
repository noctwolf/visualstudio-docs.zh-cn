---
title: LINQ to XML 动态属性 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0455f47c-4a68-4f2e-a3f8-dd1d85b99012
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f5153740a93a60bd89b193ae398008541d06bc46
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479715"
---
# <a name="linq-to-xml-dynamic-properties"></a>LINQ to XML 动态属性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[LINQ to XML 动态属性](https://docs.microsoft.com/visualstudio/designers/linq-to-xml-dynamic-properties)。  
  
本节提供有关 LINQ to XML 中动态属性的参考信息。 具体地说，这些属性由 <xref:System.Xml.Linq.XAttribute> 命名空间中的 <xref:System.Xml.Linq.XElement> 和 <xref:System.Xml.Linq> 类公开。  
  
 如 [使用 LINQ to XML 进行 WPF 数据绑定概述](../designers/wpf-data-binding-with-linq-to-xml-overview.md) 主题中所述，每个动态属性都等效于同一类中的标准公共属性或方法。 多数情况下应使用这些标准成员；动态属性是专门为 LINQ to XML 数据绑定方案提供的。 有关这些类的标准成员的更多信息，请参见 <xref:System.Xml.Linq.XAttribute> 和 <xref:System.Xml.Linq.XElement> 参考主题。  
  
 就其解析值而论，本节中的动态属性可分为两类：  
  
-   解析为单个值的简单动态属性，如 `Value` 和 <xref:System.Xml.Linq.XAttribute> 类中的 <xref:System.Xml.Linq.XElement> 属性。  
  
-   解析为索引器类型的索引值，如 [Elements](../designers/elements-xelement-dynamic-property.md) 和 <xref:System.Xml.Linq.XElement> 的 [Descendants](../designers/descendants-xelement-dynamic-property.md) 属性。 对于要解析为所需值或集合的索引器类型，必须为其传递展开名称参数。  
  
 返回 <xref:System.Collections.Generic.IEnumerable%601> 类型索引值的所有动态属性都使用延迟执行。 有关延迟执行的详细信息，请参阅 [LINQ 查询简介 (C#)](http://msdn.microsoft.com/library/37895c02-268c-41d5-be39-f7d936fa88a8)。  
  
## <a name="in-this-section"></a>本节内容  
  
|主题|描述|  
|-----------|-----------------|  
|[XAttribute 类动态属性](../designers/xattribute-class-dynamic-properties.md)|提供有关由 <xref:System.Xml.Linq.XAttribute> 类公开的动态属性的详细信息。|  
|[XElement 类动态属性](../designers/xelement-class-dynamic-properties.md)|提供有关由 <xref:System.Xml.Linq.XElement> 类公开的动态属性的详细信息。|  
  
## <a name="reference"></a>参考  
 <xref:System.Xml.Linq>  
  
 <xref:System.Xml.Linq.XElement?displayProperty=fullName>  
  
 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>  
  
## <a name="see-also"></a>请参阅  
 [使用 LINQ to XML 进行 WPF 数据绑定](../designers/wpf-data-binding-with-linq-to-xml.md)   
 [使用 LINQ to XML 进行 WPF 数据绑定概述](../designers/wpf-data-binding-with-linq-to-xml-overview.md)   
 [LINQ 查询简介 (C#)](http://msdn.microsoft.com/library/37895c02-268c-41d5-be39-f7d936fa88a8)



