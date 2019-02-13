---
title: 如何使用适用于 C++ 的 CTest
ms.date: 11/07/2017
ms.topic: conceptual
ms.author: mblome
manager: jillfra
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: e51b734d3a8d5ea98848a53929cb78099ba853d2
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55946920"
---
# <a name="how-to-use-ctest-for-c-in-visual-studio"></a>如何在 Visual Studio 中使用适用于 C++ 的 CTest

默认情况下，CMake（包括 CTest）作为“使用 C++ 的桌面开发”工作负载的组件集成到 Visual Studio IDE 中。 如果需要在计算机上安装它，请打开 Visual Studio 安装程序，单击“修改”按钮，然后在工作负载组件列表下选中[适用于 Visual C++ 的 CMake 工具](/cpp/ide/cmake-tools-for-visual-cpp)。

## <a name="to-write-tests"></a>编写测试

Visual Studio 中的 CMake 支持不涉及 Visual Studio 项目系统。 因此，可如同在任何 CMake 环境中一样编写和配置 CTest 测试。 有关在 Visual Studio 中使用 CMake 的详细信息，请参阅[适用于 Visual C++ 的 CMake 工具](/cpp/ide/cmake-tools-for-visual-cpp)。

## <a name="to-run-tests-visual-studio-2017-version-156"></a>运行测试（Visual Studio 2017 版本 15.6）

在 Visual Studio 2017 版本 15.6 中，CTest 与“测试资源管理器”完全集成，同时支持 Google 和 Boost 单元测试框架。 默认情况下，这些框架作为组件包含在“使用 C++ 的桌面开发”工作负载中。 但是，如果你要从较旧版本的 Visual Studio 升级项目，可能需要通过使用 Visual Studio 安装程序来安装这些框架。

下图显示使用 Google Test 框架的 CTest 运行结果：

![使用 VS2017 15.6 中的 Google Test 框架进行 CTest](media/ctest-test-explorer.png)

如果使用的是 CTest 而不是 Google 或 Boost 适配器，你将看到 CTest 级别而非单个测试方法级别的结果。 可以调试并单步调试仅限 CTest 的可执行文件，但不支持单个测试上的堆栈跟踪。

## <a name="to-run-tests-visual-studio-2017-version-155"></a>运行测试（Visual Studio 2017 版本 15.5）

在 Visual Studio 2017 版本 15.5中，CTest 没有与“测试资源管理器”集成。 可以通过 CMake 主菜单或“解决方案资源管理器”中 CMakeLists.txt 文件的右键单击菜单来运行测试。 测试结果会定向到 Visual Studio 输出窗口。

![在 VS2017 15.5 中运行 CTest 测试](media/cpp-cmake-run-tests.png)

## <a name="see-also"></a>请参阅

[编写适用于 C/C++ 的单元测试](writing-unit-tests-for-c-cpp.md)