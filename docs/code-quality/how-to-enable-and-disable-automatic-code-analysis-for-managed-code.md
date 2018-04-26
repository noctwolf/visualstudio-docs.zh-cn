---
title: 如何：启用和禁用托管代码的自动代码分析
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 6786d3f93c1ab7026c8a6bde25f5c43cb999e08a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>如何： 启用和禁用托管代码的自动代码分析

你可以配置代码分析，以在托管的代码项目的每个生成后运行。 你可以设置不同的代码分析属性，每个生成配置。

## <a name="to-enable-or-disable-automatic-code-analysis"></a>若要启用或禁用自动代码分析

1. 在**解决方案资源管理器**，右键单击该项目，然后选择**属性**。

1. 在项目属性对话框中，选择**代码分析**。

1. 指定中的生成类型**配置**和中的目标平台**平台**。

1. 若要启用或禁用自动代码分析，请选择或清除**生成时启用代码分析**复选框。
