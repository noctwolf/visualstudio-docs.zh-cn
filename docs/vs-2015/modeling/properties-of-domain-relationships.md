---
title: 域关系的属性 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, domain relationships
ms.assetid: 9ccb3dc2-b80c-4585-932f-3c5f87bafbcd
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: ff37703643dc9d1c795fe10b5f24154ee46174af
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469621"
---
# <a name="properties-of-domain-relationships"></a>域关系的属性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[属性的域关系](https://docs.microsoft.com/visualstudio/modeling/properties-of-domain-relationships)。  
  
下表中的属性是与域关系相关联。 有关域关系的信息，请参阅[了解模型、 类和关系](../modeling/understanding-models-classes-and-relationships.md)。 有关如何使用这些属性的详细信息，请参阅[自定义和扩展域特定语言](../modeling/customizing-and-extending-a-domain-specific-language.md)。  
  
|属性|描述|默认|  
|--------------|-----------------|-------------|  
|访问修饰符|域关系的访问级别 (`public`或`internal`)。|`public`|  
|自定义特性|用于将属性添加到生成的域关系中的源代码类。|\<无 >|  
|生成双派生|如果`True`，生成的基类和一个分部类 （以支持通过重写自定义）。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|`False`|  
|具有自定义构造函数|如果`True`，表示自定义构造函数不提供的源代码中。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|`False`|  
|继承修饰符|说明生成自域关系的源代码类继承的类型 (`none`，`abstract`或`sealed`)。|\<无 >|  
|允许存在重复项|如果`True`，域关系的重复链接可能会创建相同的两个元素之间。|`False`|  
|基关系|如果派生的域关系，域关系的基本关系。|\<无 >|  
|嵌入|如果`True`，域关系是嵌入关系。 如果`False`，关系是引用关系。|\<同时 >|  
|name|域关系的名称。|当前名称|  
|命名空间|与域关系相关联的命名空间。|当前命名空间|  
|说明|与域关系相关联的非正式说明。|\<无 >|  
|描述|说明用于记录代码和生成的设计器在 UI 中使用。|\<无 >|  
|显示名称|域关系生成的设计器中显示的名称。|\<无 >|  
|帮助关键字|可选的关键字用于编制索引的域关系的 F1 帮助。|\<无 >|  
  
## <a name="see-also"></a>请参阅  
 [域特定语言工具术语表](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



