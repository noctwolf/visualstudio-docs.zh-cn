---
title: C + + 概述的代码分析 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 27
author: corob-msft
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 42de573efcc44437eddf0e7d098681d05c094131
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49222035"
---
# <a name="code-analysis-for-cc-overview"></a>C/C++ 代码分析概述
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

C/C++ 代码分析工具为开发人员提供有关其 C/C++ 源代码中可能存在的缺陷的信息。 该工具报告的常见编码错误包括缓冲区溢出、内存未初始化、null 指针取消引用，以及内存和资源泄漏。  
  
## <a name="ide-integrated-development-environment-integration"></a>IDE（集成开发环境）集成  
 以方便开发人员可以使用分析工具，它完全集成在[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]IDE。 在生成过程中，为源代码生成任何警告都显示在错误列表中。 可以导航到导致该警告的源代码，并可以查看有关原因和可能的问题的解决方案的其他信息。  
  
## <a name="pragma-support"></a>#pragma 支持  
 开发人员可以使用`#pragma`指令以将警告视为错误; 启用或禁用警告，并禁止显示警告的代码的各个行。 有关详细信息，请参阅[如何： 启用和禁用特定的 C/c + + 警告的代码分析](http://msdn.microsoft.com/en-us/910b8518-71f1-4b2e-b012-70647795642a)。  
  
## <a name="annotation-support"></a>批注的支持  
 批注可以提高代码分析的准确性。 批注函数参数上提供有关预处理脚本和后续条件的其他信息和返回类型。 有关详细信息，请参阅[如何： 使用 __analysis_assume 指定其他代码信息](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)  
  
## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>签入策略的一部分运行分析工具  
 你可能需要所有源的代码签入行为都满足特定的策略。 具体而言，你想要确保分析最新的本地生成的步骤的形式运行。 有关启用代码分析签入策略的详细信息，请参阅[创建和签入策略使用代码分析](../code-quality/creating-and-using-code-analysis-check-in-policies.md)  
  
## <a name="team-build-integration"></a>Team Build 集成  
 您可以使用生成系统的集成的功能的步骤的形式运行代码分析工具[!INCLUDE[esprtfs](../includes/esprtfs-md.md)]生成过程。 有关详细信息，请参阅[生成应用程序](http://msdn.microsoft.com/library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)。  
  
## <a name="command-line-support"></a>命令行支持  
 除了完全集成的开发环境，开发人员还可以使用命令行中的分析工具，如下面的示例中所示：  
  
 `C:\>cl /analyze Sample.cpp`



