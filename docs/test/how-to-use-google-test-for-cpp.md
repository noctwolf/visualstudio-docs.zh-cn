---
title: "如何在 Visual Studio 中使用适用于 C++ 的 Google Test | Microsoft Docs"
ms.date: 11/04/2017
ms.technology: vs-ide-test
ms.topic: article
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: 35cc31bbe7a1d83270035217dc36fce5f3a8ab6d
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-use-google-test-for-c-in-visual-studio"></a>如何在 Visual Studio 中使用适用于 C++ 的 Google Test
在 Visual Studio 2017 版本 15.5 和更高版本中，Google Test 作为“使用 C++ 的桌面开发”工作负荷的默认组件集成到 Visual Studio IDE 中。 若要验证是否在计算机上安装了它，请打开 Visual Studio 安装程序，在工作负荷组件列表下找到 Google Test：

![安装 Google Test](media/cpp-google-component.png "安装适用于 C++ 的 Google Test")

## <a name="add-a-google-test-project-to-the-solution"></a>向解决方案添加 Google Test 项目
1. 在“解决方案资源管理器”中，右键单击解决方案节点，然后选择“添加”|“新建项目”。
2. 在左窗格中，选择“Visual C++”|“测试”，然后在中心窗格中选择“Google Test 项目”。
3. 为测试项目提供名称，然后单击“确定”。

![新 Google Test 项目](media/cpp-gtest-new-project.png "添加新 Google Test 项目")

## <a name="configure-the-test-project"></a>配置测试项目
在出现的“测试项目配置”对话框中，可以选择要测试的项目。 选择一个项目时，Visual Studio 会添加对所选项目的引用。 如果你不选择任何项目，则需要手动添加对要测试的项目的引用。 在 Google Test 二进制文件的静态和动态链接之间进行选择时，注意事项与任何 C++ 程序相同。 有关详细信息，请参阅 [Visual C++ 中的 DLL](/cpp/build/dlls-in-visual-cpp)。

 ![配置 Google Test 项目](media/cpp-gtest-config.png "Configure Google Test Project")

## <a name="set-additional-options"></a>设置附加选项
从主菜单中，选择“工具”|“选项”|“Google Test 测试适配器”以设置附加选项。 有关这些设置的详细信息，请参阅 Google Test 文档。

 ![Google Test 项目设置](media/cpp-gtest-settings.png "Google Test Project settings")

## <a name="add-include-directives"></a>添加 include 指令
在测试 .cpp 文件中，添加任何所需的 `#include` 指令以使程序的类型和函数对测试代码可见。 通常，程序在文件夹层次结构中的上一层。 如果键入 `#include "../"`，则会出现一个 IntelliSense 窗口，使你可以选择头文件的完整路径。

![添加 #include 指令](media/cpp-gtest-includes.png "将 include 指令添加到测试 .cpp 文件")

## <a name="write-and-run-tests"></a>编写和运行测试
现在已准备就绪，可以编写和运行 Google Test。 有关测试宏的信息，请参阅 [Google Test 入门](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md)。 有关使用“测试资源管理器”发现、运行和分组测试的信息，请参阅[使用测试资源管理器运行单元测试](run-unit-tests-with-test-explorer.md)。

## <a name="see-also"></a>请参阅
[编写 C/C++ 单元测试](writing-unit-tests-for-c-cpp.md)










