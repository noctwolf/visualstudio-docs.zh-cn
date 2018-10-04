---
title: 类图上 UML 关联的属性 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.teamarch.common.association.properties
helpviewer_keywords:
- UML, element properties
ms.assetid: f82bcd34-7903-4c00-8da1-613efa07d223
caps.latest.revision: 26
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: 96dc1d942a06e4030992889970fd3946d2e4d9d4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468902"
---
# <a name="properties-of-associations-on-uml-class-diagrams"></a>UML 类图上关联的属性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[属性关联在 UML 类图](https://docs.microsoft.com/visualstudio/modeling/properties-of-associations-on-uml-class-diagrams)。  
  
在 UML 类图中，可以绘制*关联*任意类型对之间。 类型是类、接口或枚举。  
  
 关联指示你正在开发的系统存储关联类型的实例之间某种类型的链接。 通常情况下，它并不表示有关链接的实现的任何内容。 例如，它们可能是指针、表中的行、XML 中交叉引用的名称等。  
  
 关联是显示特性或特性对的图示方法。 例如，如果已定义 Restaurant 类具有 Menu 类型的特性，则可通过绘制 Restaurant 和 Menu 间的关联来说明相同的定义。  
  
 若要绘制关联，请单击**关联**在工具箱中，单击第一种类型，则第二个。 可以两次单击相同的类型，以显示实例可以与相同类型的其他实例相链接。  
  
## <a name="properties"></a>属性  
 这些都是 UML 类图上的关联的属性。  
  
 要查看关联的属性，请右键单击关联，然后单击**属性**。 这些属性将显示在“属性”窗口中。  
  
 某些属性在关系图中也可见，如以下插图所示。  
  
 ![针对关联的属性](../modeling/media/uml-classprop.png "UML_ClassProp")  
  
|**Property**|描述|  
|------------------|-----------------|  
|**名为 (1)**|标识关联。 也显示在关联中点附近的关系图上。|  
|**限定的名称**|唯一地标识关联。 使用包含关联的第一个角色的包的限定名称作为前缀。|  
|**工作项**|链接到此关联的工作项数目。 若要链接工作项，请参阅[链接模型元素和工作项](../modeling/link-model-elements-and-work-items.md)。|  
|**颜色**|连接符的颜色。 与其他属性不同，这是此关联视图的属性，而不是模型中的基础关系的属性。|  
|**第一个角色**<br /><br /> **第二个角色**|关联的每个端均称为一个角色。 每个角色都描述关联的相对端处的类上的等效特性的特性。<br /><br /> 在示例图中，菜单和菜单项之间的关联具有名为 Menu 和 Contents 的角色。<br /><br /> Contents 是 Menu 类上的特性的名称。|  
  
### <a name="properties-of-each-role"></a>每个角色的属性  
 若要查看每个角色的属性，请展开**第一个角色**或**第二个角色**属性。  
  
|**Property**|**默认**|描述|  
|------------------|-----------------|-----------------|  
|**角色名称 (2)**|此角色的类型名称|角色的名称。 显示在关系图中的关联端附近。|  
|**聚合**|无|**无**(4)-表示类的实例之间的常规关系。<br /><br /> **复合**(5)-此角色处的对象包含相反角色处的对象。 可以使用**复合**工具来创建与复合聚合的关联。<br /><br /> **共享**(6)-此角色的对象包含对其他角色处的对象的引用。 可以使用**聚合**工具来创建与共享聚合的关联。<br /><br /> 确切的解释对本地约定开放。|  
|**派生**|False|如果为 true，则通过其他特性和关联计算链接的这一端的对象。 例如，通过 MyEmployer.WorkPlace 计算 MyWorkPlace。 应在“描述”或附加“注释”中键入详细信息。|  
|**是派生的并集**|False|如果为 true，则角色为派生类型中一组角色的联合。|  
|**是可导航**|True|可以在此方向读取关联。 给定相反角色的实例，则你正在描述的软件便可以高效地确定此角色中关联的实例。<br /><br /> 如果一个角色是可导航的，而另一个不可导航，则会在可导航方向中的关联上出现一个箭头 (7)。<br /><br /> 默认情况下，关联工具会创建一个在某一方向上可导航的关联。 若要将其转换为双向关联，可以选择的关联，单击该操作标记，将出现，然后单击**成为双向**。|  
|**是只读的**|False|如果为 true，则创建关联实例后不能更改它。 链接始终指向同一对象。|  
|**重数 (3)**|1|**1** -始终关联的此端链接到一个对象。 在图中，每个菜单项都有一个菜单。<br /><br /> **0..1** -以下两项关联的此端链接到一个对象，或不存在链接。<br /><br /> **\*** -关联另一端的每个对象链接到的这一端的对象的集合，该集合可能为空。<br /><br /> **1..\***  -关联另一端的每个对象链接到此端的至少一个对象。 在图中，每个菜单都有至少一个菜单项。<br /><br /> *n* **..** *m* -在另一端的每个对象具有一系列之间*n*并*m*链接到此端的对象。|  
|**有序**|False|如果为 true，则返回的集合会构成一个顺序列表。 对于大于 1 的重数。|  
|**是唯一的**|False|如果为 true，则返回的集合中没有重复值。 对于大于 1 的重数。|  
|**可见性**|Public|公共 - 全局可见<br /><br /> 专用 - 对所属类型以外的类型不可见<br /><br /> 受保护 - 对派生自所有者的类型可见<br /><br /> 包 - 对同一包中的其他类型可见。|  
  
## <a name="see-also"></a>请参阅  
 [UML 类图： 参考](../modeling/uml-class-diagrams-reference.md)   
 [UML 类图上类型的属性](../modeling/properties-of-types-on-uml-class-diagrams.md)   
 [UML 类图上特性的属性](../modeling/properties-of-attributes-on-uml-class-diagrams.md)   
 [UML 类图上的操作的属性](../modeling/properties-of-operations-on-uml-class-diagrams.md)   
 [UML 类图：准则](../modeling/uml-class-diagrams-guidelines.md)


