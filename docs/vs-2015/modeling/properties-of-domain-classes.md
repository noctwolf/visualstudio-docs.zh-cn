---
title: 域类的属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, domain class
ms.assetid: a3993995-19e7-4761-a972-b1de89131a1b
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: f9f84290ca8155cb2cf2b48a5d9b3f5f68c7ce9a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49172622"
---
# <a name="properties-of-domain-classes"></a>域类的属性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

域类具有下表中的属性。 域类的相关信息，请参阅[了解模型、 类和关系](../modeling/understanding-models-classes-and-relationships.md)。 有关如何使用这些属性的详细信息，请参阅[自定义和扩展域特定语言](../modeling/customizing-and-extending-a-domain-specific-language.md)。  
  
|属性|描述|默认|  
|--------------|-----------------|-------------|  
|访问修饰符|域类的访问级别（`public` 或 `internal`）。|`public`|  
|自定义特性|用于将属性添加到此域类从生成的源代码类。|\<无 >|  
|生成双派生|如果`True`，将生成的基类和一个分部类 （以支持通过重写自定义）。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|`False`|  
|具有自定义构造函数|如果`True`，将在源代码中提供自定义构造函数。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|`False`|  
|继承修饰符|介绍的从域类生成的源代码类的继承的类型 (`none`，`abstract`或`sealed`)。|`none`|  
|基类|如果此域类派生，类的基类的名称。|\<无 >|  
|name|此域类的名称。|当前名称|  
|命名空间|此域类的命名空间。|当前命名空间|  
|说明|此域类相关联的非正式说明。|\<无 >|  
|描述|用于记录生成的设计器的 UI 说明。|\<无 >|  
|显示名称|将此域类生成的设计器中显示的名称。|\<无 >|  
|帮助关键字|用于索引此域类的 F1 帮助中的可选关键字。|\<无 >|  
  
## <a name="see-also"></a>请参阅  
 [域特定语言工具术语表](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



