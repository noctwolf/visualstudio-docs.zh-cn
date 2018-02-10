---
title: "DSL 定义的属性 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, definition file
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5ccf6937aa3c317feb81a907348d41e4d322d346
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="properties-of-a-dsl-definition"></a>DSL 定义的属性
DslDefinition 属性定义*域特定语言*如版本编号定义属性。 DslDefinition 属性将显示在**属性**窗口时单击打开中的关系图的区域*域特定语言设计器*。  
  
 有关详细信息，请参阅[如何定义域特定语言](../modeling/how-to-define-a-domain-specific-language.md)。 有关如何使用这些属性的详细信息，请参阅[自定义和扩展的域特定语言](../modeling/customizing-and-extending-a-domain-specific-language.md)。  
  
 DslDefinition 具有下表中的属性：  
  
|属性|描述|默认|  
|--------------|-----------------|-------------|  
|访问修饰符|确定域类的访问修饰符是否为公共或内部。|public|  
|自定义特性|自定义域类的属性。<br /><br /> **请注意**使用浏览按钮将属性添加。|\<none>|  
|公司名称|系统注册表中的当前公司名称的名称。|当前的公司名称|  
|name|此域类的名称。|当前的名称|  
|命名空间|与此域类关联的命名空间。|当前命名空间|  
|包 Guid|Guid[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]为此 DSL 生成的包。|\<none>|  
|包 Namespace|命名空间[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]为此 DSL 生成的包。|\<none>|  
|产品名称|将为注册产品的名称[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]为此 DSL 生成的包。|\<none>|  
|说明|与此域类相关联的注释。|\<none>|  
|描述|此域类的说明。|\<none>|  
|显示名称|将此域类的生成设计器中显示的名称。|\<none>|  
|帮助关键字|与此域类关联的帮助关键字。|\<none>|  
|生成|此域特定语言定义增量生成号。|0|  
|主要版本|有关此域特定语言定义的增量的主要版本号。|1|  
|次要版本|有关此域特定语言定义的增量的次要版本号。|0|  
|Revision|有关此域特定语言定义的递增修订版本号。|0|  
  
## <a name="see-also"></a>请参阅  
 [域特定语言工具词汇表](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)