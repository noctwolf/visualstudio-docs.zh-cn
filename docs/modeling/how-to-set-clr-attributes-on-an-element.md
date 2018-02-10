---
title: "如何： 在元素上设置 CLR 特性 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 1eedf41931c7f9476691e507ab0afcd9e2a4c4ee
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>如何：在元素上设置 CLR 特性
自定义特性是可以添加到域元素、 形状、 连接器和关系图的特殊属性。 你可以添加任何特性的继承自`System.Attribute`类。  
  
### <a name="to-add-a-custom-attribute"></a>若要添加的自定义特性  
  
1.  在**DSL 资源管理器**，选择你想要添加的自定义特性的元素。  
  
2.  在**属性**窗口中，到下的一步**自定义特性**属性，单击浏览 (**...**) 图标。  
  
     **编辑属性**对话框随即打开。  
  
3.  在**名称**列中，单击**\<添加属性 >**并键入特性的名称。 按 Enter。  
  
4.  在属性名称的行显示括号。 在此行上键入该属性的参数类型 (例如， `string`)，然后按 ENTER。  
  
5.  在**Name 属性**列中，键入适当的名称，例如`MyString`。  
  
6.  单击 **“确定”**。  
  
     **自定义特性**属性现在显示的属性采用以下格式：  
  
     `[` *AttributeName* `(` *ParameterName* `=` *Type* `)]`  
  
## <a name="see-also"></a>请参阅  
 [域特定语言工具词汇表](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)