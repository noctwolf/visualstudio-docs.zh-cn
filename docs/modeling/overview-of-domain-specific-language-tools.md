---
title: 域特定语言工具的概述 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: cd105ae8553d39a6fe1a1bd23136d5027da17ec3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="overview-of-domain-specific-language-tools"></a>域特定语言工具的概述
域特定语言工具 （DSL 工具），它承载在[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]，但仍使设计的域特定语言，然后生成用户必须具有创建基于语言的模型的所有内容。  
  
 DSL 工具中包含的以下工具：  
  
-   使用不同的解决方案模板来帮助你开始开发你的域特定语言项目向导。  
  
-   图形设计器用于创建和编辑你的域特定语言的定义。  
  
-   确保验证引擎的域特定语言定义的格式正确，并显示错误和警告，如果有问题。  
  
-   代码生成器，采用的域特定语言定义作为输入并且生成作为输出的源代码。  
  
## <a name="the-dsl-tools-solution"></a>DSL 工具解决方案  
 特定于域的设计器向导提供了以下的解决方案模板：  
  
-   任务流  
  
-   类图  
  
-   最小的语言  
  
-   组件模型  
  
-   最小的 WPF  
  
-   最小 Windows.Forms  
  
-   DSL 库  
  
 有关详细信息，请参阅[选择的域特定语言解决方案模板](../modeling/choosing-a-domain-specific-language-solution-template.md)。  
  
 此向导将创建[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]解决方案，它具有以下项目：  
  
-   dsl  
  
     Dsl 项目定义的域特定语言和及其编辑和处理的工具。  
  
-   **DslPackage**  
  
     DslPackage 项目确定如何将语言工具与集成[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。  
  
## <a name="the-dsl-tools-graphical-interface"></a>DSL 工具图形界面  
 DSL 工具图形界面可用于将元素和关系添加到你的域特定语言。 添加元素后，你可以通过将其映射到形状、 自定义颜色，以及添加修饰符定义其外观。 你还可以将元素添加到工具箱。  
  
## <a name="validation-in-dsl-tools"></a>DSL 工具中的验证  
 Dsl 提供一层验证以确保域模型代码生成满足的基本要求。 通常情况下，在创建你自己的域特定语言时，你应该添加你自己的验证来表示您的业务逻辑规则。 有关自定义验证的详细信息，请参阅[域特定语言中的验证](../modeling/validation-in-a-domain-specific-language.md)。  
  
 我们建议你设计时通常验证你的域特定语言。 如果你的域特定语言具有验证错误，无法生成源代码。 从模板生成源代码的过程执行通过单击**转换所有模板**解决方案资源管理器工具栏中。 每当你修改语言定义，还请确保**转换所有模板**。 有关详细信息，请参阅[如何： 创建域特定语言解决方案](../modeling/how-to-create-a-domain-specific-language-solution.md)。  
  
## <a name="customization-of-dsl-tools"></a>DSL 工具的自定义  
 你可以提供额外的代码来优化模型的行为并通过你的语言定义约束。 如有必要，你可以通过修改文本模板进行重要更改。  
  
## <a name="distributing-your-dsl-solution"></a>分发 DSL 解决方案  
 DSL 工具生成中承载的包[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。 包显示工具箱、 的 DSL 资源管理器中和其他 UI 元素，用户可以通过使用你的域特定语言创建模型。  
  
 当生成并运行 DSL 工具解决方案[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]，第二个实例[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]显示语言的用户看到你的域特定语言的样子。 验证一切是否正常工作后，你可以将分发`.vsix`你将在 DslPackage 项目的生成文件夹中找到的文件。 此文件可以用于安装作为 DSL[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]在其他计算机上的扩展。  有关详细信息，请参阅[部署域特定语言解决方案](../modeling/deploying-domain-specific-language-solutions.md)。  
  
## <a name="see-also"></a>另请参阅  
 [实验实例](../extensibility/the-experimental-instance.md)   
 [域特定语言工具词汇表](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)