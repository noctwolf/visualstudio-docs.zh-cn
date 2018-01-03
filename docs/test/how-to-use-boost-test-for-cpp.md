---
title: "如何在 Visual Studio 中使用适用于 C++ 的 Boost.Test | Microsoft Docs"
ms.custom: 
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0710a8-8e8a-4f6e-8415-5ab3eb830079
caps.latest.revision: "14"
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af55f9f124b2ec609c4f0a590e7c2fab738624d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-boosttest-for-c-in-visual-studio"></a>如何在 Visual Studio 中使用适用于 C++ 的 Boost.Test
在 **Visual Studio 2017 版本 15.5** 和更高版本中，Boost.Test 作为“使用 C++ 的桌面开发”工作负荷的组件集成到 Visual Studio IDE 中。 若要在计算机上安装它，请打开 Visual Studio 安装程序，在工作负荷组件列表下找到“Boost.Test 适配器”：

![安装 Boost Test](media/cpp-boost-component.png "安装适用于 C++ 的 Boost.Test")

## <a name="install-boost"></a>安装 Boost

 Boost.Test 需要[Boost](http://www.boost.org/)！ 如果未安装 Boost，则建议使用 Vcpkg 程序包管理器。 

1. 按照 [Vcpkg：适用于 Windows 的 C++ 程序包管理器](/cpp/vcpkg)中的说明来安装 vcpkg（如果尚未安装）。
2. 运行 `vcpkg install boost` 以安装 Boost 库。
3. 运行 `vcpkg integrate install` 命令以使用该库以及 Boost 头文件和二进制文件的包含路径配置 Visual Studio。 

## <a name="create-a-project-for-your-tests"></a>为测试创建项目
在 Visual Studio 2017 版本 15.5 中，没有预配置测试项目或项模板可用于 Boost.Test。 因此，必须创建控制台应用程序项目来存放测试。 计划在 Visual Studio 的未来版本中包含适用于 Boost.Test 的测试模板。 

1. 在“解决方案资源管理器”中，右键单击解决方案节点，然后选择“添加”|“新建项目”。 
2. 在左窗格中，选择“Windows 桌面”，然后在中心窗格中选择“Windows 控制台应用程序”。 
3. 为项目提供名称，然后单击“确定”。 

## <a name="add-include-directives"></a>添加 include 指令
在测试 .cpp 文件中，添加任何所需的 `#include` 指令以使程序的类型和函数对测试代码可见。 通常，程序在文件夹层次结构中的上一层。 如果键入 `#include "../"`，则会出现一个 IntelliSense 窗口，使你可以选择头文件的完整路径。

![添加 #include 指令](media/cpp-gtest-includes.png "将 include 指令添加到测试 .cpp 文件")

至少需要使用 `#include <path>/unit_test.hpp` 包含 [Boost.Test 的单个头文件变量](http://www.boost.org/doc/libs/1_48_0/libs/test/doc/html/utf/user-guide/usage-variants/single-header-variant.html)，并定义 `BOOST_TEST_MODULE`。 下面的示例足以使测试可在“测试资源管理器”中被发现：

```cpp
#include "stdafx.h"
#define BOOST_TEST_MODULE MyTest
#include <boost/test/included/unit_test.hpp>
#include "../MyProgram/MyClass.h" // project being tested
#include <string>

BOOST_AUTO_TEST_CASE(my_boost_test)
{
    std::string name = "Bill";
    MyClass mc(name);
    Assert::AreEqual();
    BOOST_CHECK(name == mc.GetName());
}
```

## <a name="write-and-run-tests"></a>编写和运行测试
现在已准备就绪，可以编写和运行 Boost Test。 有关测试宏的信息，请参阅 [Boost Test 库文档](http://www.boost.org/doc/libs/1_38_0/libs/test/doc/html/index.html)。 有关使用“测试资源管理器”发现、运行和分组测试的信息，请参阅[使用测试资源管理器运行单元测试](run-unit-tests-with-test-explorer.md)。

## <a name="see-also"></a>请参阅
[编写 C/C++ 单元测试](writing-unit-tests-for-c-cpp.md)


  







