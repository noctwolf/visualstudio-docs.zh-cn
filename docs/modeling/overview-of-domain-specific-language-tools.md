---
title: 域特定语言工具的概述
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 873c377b4b2262df6b12f581f1cdac901d27ffce
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47859427"
---
# <a name="overview-of-domain-specific-language-tools"></a>域特定语言工具的概述
域特定语言工具 （DSL 工具），承载于 Visual Studio 中，可以设计一种域特定语言，然后生成用户必须具有创建基于语言的模型的所有内容。

 DSL 工具包含以下工具：

-   使用不同的解决方案模板来帮助你开始开发你的域特定语言项目向导。

-   用于创建和编辑你的域特定语言定义的图形设计器。

-   验证引擎，可确保域特定语言定义的格式正确，并显示错误和警告，如果出现问题。

-   代码生成器，它将作为输入的域特定语言定义，并生成作为输出的源代码。

## <a name="the-dsl-tools-solution"></a>DSL 工具解决方案
 特定于域的设计器向导提供了以下解决方案模板：

-   任务流

-   类图

-   最小语言

-   组件模型

-   最小 WPF

-   最小 Windows.Forms

-   DSL 库

 有关详细信息，请参阅[选择域特定语言解决方案模板](../modeling/choosing-a-domain-specific-language-solution-template.md)。

 向导将创建具有以下项目的 Visual Studio 解决方案：

-   Dsl

     在 Dsl 项目定义的特定于域的语言和其编辑功能和正在处理的工具。

-   **DslPackage**

     在 DslPackage 项目确定的语言工具与 Visual Studio 的集成。

## <a name="the-dsl-tools-graphical-interface"></a>DSL 工具的图形界面
 DSL 工具的图形界面可用于将元素和关系添加到你的特定于域的语言。 添加元素后，可以通过将其映射到形状、 自定义颜色，并添加修饰器来定义其外观。 此外可以向工具箱添加元素。

## <a name="validation-in-dsl-tools"></a>DSL 工具中的验证
 Dsl 提供了一个级别的验证，以确保域模型代码生成满足基本要求。 通常情况下，当您创建您自己的特定于域的语言，则添加您自己的验证来表达业务逻辑规则。 有关自定义验证的详细信息，请参阅[特定于域的语言中的验证](../modeling/validation-in-a-domain-specific-language.md)。

 我们建议在设计时经常验证您的特定于域的语言。 如果你的域特定语言具有验证错误，无法生成源代码。 从模板生成源代码的过程执行通过单击**转换所有模板**的解决方案资源管理器工具栏中。 只要修改语言定义，还请确保**转换所有模板**。 有关详细信息，请参阅[如何： 创建域特定语言解决方案](../modeling/how-to-create-a-domain-specific-language-solution.md)。

## <a name="customization-of-dsl-tools"></a>DSL 工具的自定义
 你可以提供其他代码来优化模型的行为，并通过您的语言定义的约束。 如果需要，可以通过修改文本模板中进行重大更改。

## <a name="distributing-your-dsl-solution"></a>分发你的 DSL 解决方案
 DSL 工具在 Visual Studio 中生成承载的包。 包将显示一个工具箱、 DSL 资源管理器和其他 UI 元素，用户可以通过使用特定于域的语言来创建模型。

 当生成并运行 DSL 工具解决方案在 Visual Studio 中时，Visual Studio 的第二个实例将显示于用户的语言中特定于域的语言的外观。 验证是否一切运行正常之后，可以将分发`.vsix`您将在 DslPackage 项目的生成文件夹中找到的文件。 此文件可以用于为其他计算机上的 Visual Studio 扩展安装 DSL。  有关详细信息，请参阅[部署域特定语言解决方案](../modeling/deploying-domain-specific-language-solutions.md)。

## <a name="see-also"></a>请参阅

- [实验实例](../extensibility/the-experimental-instance.md)
- [域特定语言工具术语表](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)