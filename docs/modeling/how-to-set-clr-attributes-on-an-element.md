---
title: "如何： 在元素上设置 CLR 特性 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.EditAttributesDialog
helpviewer_keywords: Domain-Specific Language, custom attrributes
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 91f1143e593ae63d41e15beb74612f192ec736d1
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
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
  
     `[`*AttributeName* `(` *ParameterName* `=` *类型*`)]`  
  
## <a name="see-also"></a>请参阅  
 [域特定语言工具词汇表](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)