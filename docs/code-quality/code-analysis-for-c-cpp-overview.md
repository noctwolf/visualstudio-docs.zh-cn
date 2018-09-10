---
title: C/C++ 代码分析概述
ms.date: 04/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- annotations, code analysis
- build integration, code analysis
- C/C++ code analysis
- IDE, code analysis
- pragma directive, code analysis
- code analysis, C/C++
- code analysis tool
- command line, code analysis
- C++, code analysis
- check-in policies, code analysis
- '#pragma directives, code analysis'
- C, code analysis
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: 152d57b0b1d1659883a9096c84b650ad192c34d1
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44280982"
---
# <a name="code-analysis-for-cc-overview"></a>代码分析 C/c + + 概述

C/c + + 代码分析工具提供了有关 C/c + + 源代码中可能存在的缺陷的信息。 工具报告的常见编码错误包括缓冲区溢出、内存未初始化、null 指针取消引用以及内存和资源泄漏。 该工具还可以运行针对检查[c + + Core Guidelines](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)。

## <a name="ide-integrated-development-environment-integration"></a>IDE （集成的开发环境） 集成

在 Visual Studio ide 完全集成的代码分析工具。

在生成过程中，为源代码生成任何警告都显示在错误列表中。 可以导航到导致该警告的源代码，并可以查看有关原因和可能的问题的解决方案的其他信息。

## <a name="command-line-support"></a>命令行支持

此外可以使用命令行中的分析工具，如下面的示例中所示：

```cmd
C:\>cl /analyze Sample.cpp
```

**Visual Studio 2017 版本 15.7 及更高版本**可以从命令行运行该工具，包括 CMake 任何生成系统。

## <a name="pragma-support"></a>#pragma 支持

可以使用`#pragma`指令以将警告视为错误; 启用或禁用警告，并禁止显示警告的代码的各个行。 有关详细信息，请参阅[如何： 为 C/c + + 项目中设置代码分析属性](how-to-set-code-analysis-properties-for-c-cpp-projects.md)。

## <a name="annotation-support"></a>批注的支持

批注可以提高代码分析的准确性。 批注函数参数上提供有关预处理脚本和后续条件的其他信息和返回类型。 有关详细信息，请参阅[如何： 使用 __analysis_assume 指定其他代码信息](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)

## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>签入策略的一部分运行分析工具

你可能需要所有源的代码签入行为都满足特定的策略。 具体而言，你想要确保分析最新的本地生成的步骤的形式运行。 有关启用代码分析签入策略的详细信息，请参阅[创建和签入策略使用代码分析](../code-quality/creating-and-using-code-analysis-check-in-policies.md)

## <a name="team-build-integration"></a>Team Build 集成

您可以使用生成系统的集成的功能的步骤的形式运行代码分析工具[!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)]生成过程。 有关详细信息，请参阅[Azure 管道](/azure/devops/pipelines/index)。

## <a name="see-also"></a>请参阅

- [快速入门： C/c + + 代码分析](quick-start-code-analysis-for-c-cpp.md)
- [演练： 分析 C/c + + 代码进行缺陷](walkthrough-analyzing-c-cpp-code-for-defects.md)
- [C/C++ 代码分析警告](code-analysis-for-c-cpp-warnings.md)
- [使用 C++ Core Guidelines 检查器](using-the-cpp-core-guidelines-checkers.md)
- [C + + Core Guidelines 检查程序引用](code-analysis-for-cpp-corecheck.md)
- [使用规则集指定要运行的 C++ 规则](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
- [使用代码分析工具来分析驱动程序质量](/windows-hardware/drivers/develop/analyzing-driver-quality-by-using-code-analysis-tools)
- [代码分析驱动程序警告](/windows-hardware/drivers/devtest/prefast-for-drivers-warnings)
