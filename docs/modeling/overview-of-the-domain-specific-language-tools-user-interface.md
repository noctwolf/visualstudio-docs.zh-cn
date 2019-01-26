---
title: 域特定语言工具用户界面的概述
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.editor
helpviewer_keywords:
- Domain-Specific Language Tools, user interface
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 4cc5cf725b47c740bc14a57870e589c5de4e8c1b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54980422"
---
# <a name="overview-of-the-domain-specific-language-tools-user-interface"></a>域特定语言工具用户界面的概述
当首次在 Visual Studio 中打开的域特定语言工具 （DSL 工具） 解决方案时，用户界面类似于下图。

 ![dsl 设计器](../modeling/media/dsl_designer.png)

 下表说明了如何使用 UI 的部分。

|**元素**|**定义**|
|-|-|
|关系图|在关系图显示域模型。<br /><br /> 两个方面阐释了关系图。 一侧在模型中定义的元素的类型。 另一方定义如何将您的模型显示在屏幕上。|
|工具箱|将从工具箱添加域类和形状到关系图类型的工具。 若要添加关系、 连接器和形状映射，单击工具，然后单击关系图中，在源节点，然后目标节点。|
|DSL 资源管理器|**DSL 资源管理器**DSL 定义的活动窗口时，将出现。 它显示为树的 DSL。 DSL 资源管理器允许您编辑关系图不显示模型中的功能。 例如，可以添加工具箱项，并使用切换在验证过程**DSL 资源管理器**。|
|DSL 详细信息窗口|**DSL 详细信息**窗口显示域的属性，可以控制元素的显示方式，以及元素的复制和删除的模型的元素。<br /><br /> -默认情况下， **DSL 详细信息**窗口的旁边将出现**错误列表**并**输出**windows。|

## <a name="the-domain-model-diagram"></a>域模型关系图
 域模型关系图分为两个部分。 关系图的一侧显示模型中的元素和关系。 另一侧显示模型的方式显示，并包含用于显示元素和属性的模型关系图的形状。 下图显示了关系图中的元素。

 ![具有泳道的 dsl 设计器](../modeling/media/dsl_desinger.png)

 下表介绍了某些域模型关系图中的元素。

|**术语**|**定义**|
|-|-|
|域类|域类是在模型中的元素的类型。<br /><br /> 域类可以出现不止一次在关系图中，如果它是多个关系的目标。<br /><br /> 若要添加域类，将从域类工具**工具箱**到**类和关系**端的关系图。|
|域关系|域关系是在模型中的元素之间的链接类型。<br /><br /> *嵌入关系*指示目标元素是拥有或所包含的源元素，并显示为一条实线。 在模型中的每个元素应为一个嵌入关系的目标，以确保该模型形成一个树。 一个*引用关系*指示模型元素之间的常规链接，并显示为虚线。 任何元素可以具有任意数量的引用链接。<br /><br /> 通过单击该工具来创建关系**工具箱**、 单击源域类，并随后单击目标类。|
|形状和连接符|形状指定模型元素在 DSL 关系图上的显示方式，连接器可用于显示关系的 DSL 关系图上指定的行。<br /><br /> 若要创建形状或连接线，将工具拖至**关系图元素**端的关系图。|
|形状映射|形状地图显示为在域模型关系图中，将形状链接到域类，它将显示或连接到它将显示的域关系的连接器上的线条。|

## <a name="see-also"></a>请参阅

- [域特定语言工具的概述](../modeling/overview-of-domain-specific-language-tools.md)
- [域特定语言工具术语表](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
- [自定义和扩展域特定语言](../modeling/customizing-and-extending-a-domain-specific-language.md)