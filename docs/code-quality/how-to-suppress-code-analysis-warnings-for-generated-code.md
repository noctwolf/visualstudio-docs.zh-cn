---
title: 禁止显示生成的代码的代码分析冲突
ms.date: 05/13/2019
ms.topic: conceptual
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6a7990f5e9fa1893d8813b1307ab6a0a7fee46be
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65613566"
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>如何：禁止对生成的代码显示代码分析警告

生成的代码包括由托管的代码编译器或第三方工具添加到项目的代码。 您可能想要看到的代码分析在生成的代码中发现的规则冲突。 但是，由于您不能查看和维护包含冲突的代码，因此可能不想要查看它们。

**禁止显示生成代码的结果**项目的代码分析属性页上的复选框，可选择是否显示从第三方工具生成的代码分析警告的代码。

> [!NOTE]
> 当生成的代码所产生的代码分析错误和警告出现在窗体和模板中时，此选项不会取消显示它们。 可以查看和维护窗体或模板的源代码。

### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>若要禁止显示项目中生成代码的警告

1. 右键单击该项目中的**解决方案资源管理器**，然后单击**属性**。

2. 选择**代码分析**选项卡。

3. 选择**禁止显示生成代码的结果**复选框。

> [!NOTE]
> 仅可取消静态代码分析的警告。 目前，不能取消的代码分析警告[分析器](roslyn-analyzers-overview.md)。