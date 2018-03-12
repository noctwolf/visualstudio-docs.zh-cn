---
title: "域路径语法 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, domain path
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: fb2b1dfa13bf00c29452798253198b2ad0e72e97
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="domain-path-syntax"></a>域路径语法
DSL 定义使用类似 XPath 的语法在模型中查找特定元素。  
  
 通常，你不必直接使用此语法。 在“DSL 详细信息”或“属性”窗口中，你可以在它所显示的位置中单击向下箭头并使用路径编辑器。 但是，在使用编辑器后，该路径将以此形式显示在字段中。  
  
 域路径采用以下形式：  
  
 *RelationshipName.PropertyName/!Role*  
  
 ![CommentReferencesSubjects 引用关系](../modeling/media/dsl_reference.png "dsl_reference")  
  
 该语法将遍历模型树。 例如，域关系**CommentReferencesSubjects**在上图中具有**主题**角色。 路径段**/ ！Subjectt**指定路径完成元素通过访问**主题**角色。  
  
 每段都以域关系的名称开头。 如果遍历，从某个元素为关系的路径段将显示为*Relationship.PropertyName*。 如果跃点，从链接到的元素的路径段将显示为*关系 / ！RoleName*。  
  
 使用斜杠分隔路径的语法。 每个路径段是都从元素到链接（关系的实例）或从链接到元素的跳跃。 路径段经常成对显示。 一个路径段表示从元素到链接的跳跃，而下一个段则表示从链接到另一端的元素的跳跃。 （任何链接还可以是关系本身的源或目标）。  
  
 用于元素到链接跳跃的名称是角色的 `Property Name` 的值。 用于链接到元素跳跃的名称是目标角色名称。  
  
## <a name="see-also"></a>请参阅  
 [了解模型、类和关系](../modeling/understanding-models-classes-and-relationships.md)