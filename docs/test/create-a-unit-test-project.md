---
title: 创建单元测试项目
ms.date: 01/29/2019
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 813829e1e4024a38415cd9cef6da9fa7ca2ed87b
ms.sourcegitcommit: 9866740aec05d1a3a5dc3b4b6d2ceaeecbd3fc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55424403"
---
# <a name="create-a-unit-test-project"></a>创建单元测试项目

单元测试往往反映被测代码的结构。 例如，系统会为项目中的每个代码项目创建一个单元测试项目。 测试项目可以与成品代码位于同一解决方案中，也可以位于单独的解决方案中。 解决方案中可以有多个单元测试项目。

> [!NOTE]
> 本机代码的单元测试位置和测试项目结构可能与本文中描述的结构不同。 有关详细信息，请参阅[编写 C/C++ 单元测试](writing-unit-tests-for-c-cpp.md)。

## <a name="to-create-a-unit-test-project"></a>创建单元测试项目

1. 在“文件”菜单上选择“新建”，再选择“项目”。 或按 Ctrl+Shift+N。

2. 在“新建项目”对话框中，展开“已安装”节点，选择要用于测试项目的语言，然后选择“测试”。

3. 若要使用 Microsoft 单元测试框架之一，请从项目模板的列表中选择“单元测试项目”  。 否则，请选择你想要使用的单元测试框架的项目模板。 为项目命名，然后选择“确定”。

4. 在单元测试项目中，添加对被测代码的引用。 要添加对相同解决方案中代码项目的引用，请执行以下操作：

   1. 在解决方案资源管理器中选择测试项目。

   2. 在“项目”菜单上，选择“添加引用” 。

   3. 在“引用管理器”中，选择“项目”下的“解决方案”节点。 选择要测试的代码项目，然后选择“确定”。

   如果要测试的代码位于其他位置，请参阅[管理项目中的引用](../ide/managing-references-in-a-project.md)了解有关添加引用的信息。

## <a name="next-steps"></a>后续步骤

请参阅以下部分之一：

**编写单元测试**

- [单元测试代码](../test/unit-test-your-code.md)

- [编写 C/C++ 单元测试](writing-unit-tests-for-c-cpp.md)

- [在单元测试中使用 MSTest 框架](using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests.md)

**运行单元测试**

- [使用测试资源管理器运行单元测试](../test/run-unit-tests-with-test-explorer.md)