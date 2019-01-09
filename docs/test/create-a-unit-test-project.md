---
title: 创建单元测试项目
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 8b3b3f8af1dbc2cfd745a56238694cd19cc1f16d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53824933"
---
# <a name="create-a-unit-test-project"></a>创建单元测试项目

单元测试往往反映被测代码的结构。 例如，系统会为项目中的每个代码项目创建一个单元测试项目。 测试项目可以与成品代码位于同一解决方案中，也可以位于单独的解决方案中。 解决方案中可以有多个单元测试项目。

> [!NOTE]
> 本机代码的单元测试位置和测试项目结构可能与本主题中描述的结构不同。 有关详细信息，请参阅[编写 C/C++ 单元测试](writing-unit-tests-for-c-cpp.md)。

## <a name="to-create-a-unit-test-project"></a>创建单元测试项目：

1.  在“文件”菜单上，选择“新建”，然后选择“项目”（快捷键：Ctrl+Shift+N）。

2.  在“新建项目”对话框中，展开“已安装”节点，选择要用于测试项目的语言，然后选择“测试”。

3.  若要使用 Microsoft 单元测试框架之一，请从项目模板的列表中选择“单元测试项目”  。 否则，请选择你想要使用的单元测试框架的项目模板。 为了测试示例中的“帐户”项目，可将该项目命名为“AccountsTests”。

4.  在单元测试项目中，添加对被测代码的引用。  下面介绍了如何在同一解决方案中创建对代码项目的引用：

    1.  在解决方案资源管理器中，选择项目。

    2.  在“项目”菜单上，选择“添加引用” 。

    3.  在“引用管理器”对话框中，打开“解决方案”节点，然后选择“项目”。 检查代码项目名称并关闭对话框。

5.  如果要测试的代码位于其他位置，请参阅[管理项目中的引用](../ide/managing-references-in-a-project.md)了解有关添加引用的信息。

## <a name="next-steps"></a>后续步骤

 请参阅以下部分之一：

**编写单元测试**

- [单元测试代码](../test/unit-test-your-code.md)

- [编写 C/C++ 单元测试](writing-unit-tests-for-c-cpp.md)

- [在单元测试中使用 MSTest 框架](using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests.md)

**运行单元测试**

- [使用测试资源管理器运行单元测试](../test/run-unit-tests-with-test-explorer.md)