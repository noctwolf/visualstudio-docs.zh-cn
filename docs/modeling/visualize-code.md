---
title: 可视化代码
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- code, understanding
- code, visualizing
- code, exploring
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e1866437fae3fb5594e85299f94a075072dd6528
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53907834"
---
# <a name="visualize-code"></a>可视化代码

你可以在 Visual Studio 中使用可视化和建模工具，以帮助你了解现有代码并描述你的应用程序。 这可以让你直观地了解更改可能对代码产生的影响，并帮助你评估更改导致的工作和风险。 例如：

- 了解代码的关系，可以用可视的方式映射这些关系。

- 若要描述系统的体系结构并使代码与其设计保持一致，创建依赖项关系图，并针对这些关系图验证代码。

- 若要描述类结构，请创建类关系图。

这些工具还可以帮助你更轻松地与参与项目的人员进行沟通。

若要查看哪些版本的 Visual Studio 支持每个功能，请参阅[体系结构和建模工具的版本支持](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)

## <a name="what-do-you-want-to-do"></a>你希望做什么？

|||
|-|-|
|**了解代码和其关系：**<br /><br /> 特定代码段之间的代码图关系<br /><br /> 请参阅整个解决方案中的代码关系概述。|- [映射解决方案之间的依赖项](../modeling/map-dependencies-across-your-solutions.md)<br />- [使用代码图调试应用程序](../modeling/use-code-maps-to-debug-your-applications.md)<br />- [使用代码图分析器发现潜在问题](../modeling/find-potential-problems-using-code-map-analyzers.md)<br />- [调试时映射调用堆栈上的方法](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)|
|**了解类结构：**<br /><br /> 通过从代码创建类关系图，在项目中查看类的结构。|[如何：将类图添加到项目 （类设计器）](../ide/class-designer/how-to-add-class-diagrams-to-projects.md)|
|**描述高级系统设计和验证对此设计的代码：**<br /><br /> 通过创建依赖项关系图来描述高级系统设计和其预期的依赖项。 对此设计进行代码验证，以确保代码中的依赖项与设计保持一致。|- [从代码创建依赖项关系图](../modeling/create-layer-diagrams-from-your-code.md)<br />- [依赖项关系图：引用](../modeling/layer-diagrams-reference.md)<br />- [依赖项关系图：指导原则](../modeling/layer-diagrams-guidelines.md)<br />- [使用依赖项关系图验证代码](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="see-also"></a>请参阅

- [方案：使用可视化和建模更改设计](../modeling/scenario-change-your-design-using-visualization-and-modeling.md)
- [分析体系结构和建模](../modeling/analyze-and-model-your-architecture.md)
- [应用体系结构建模](../modeling/model-your-app-s-architecture.md)
- [在你的开发过程中使用模型](../modeling/use-models-in-your-development-process.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
