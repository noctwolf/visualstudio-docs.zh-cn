---
title: "如何在 Visual Studio 中使用适用于 C++ 的 Boost.Test | Microsoft Docs"
ms.custom: 
ms.date: 01/05/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bdf772be03f6021f499b9bf777922d6d2743e0dc
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2018
---
# <a name="how-to-use-boosttest-for-c-in-visual-studio"></a>如何在 Visual Studio 中使用适用于 C++ 的 Boost.Test

在 **Visual Studio 2017 版本 15.5** 和更高版本中，Boost.Test 测试适配器作为“使用 C++ 的桌面开发”工作负荷的组件集成到 Visual Studio IDE 中。

![Boost.Test 的测试适配器](media/cpp-boost-component.png " Boost.Test 组件的测试适配器")

如果没有安装“使用 C++ 的桌面开发”工作负载，则打开“Visual Studio 安装程序”并选择“修改”。 选择“使用 C++ 的桌面开发”工作负载，然后选择“修改”按钮。

## <a name="install-boost"></a>安装 Boost

Boost.Test 需要[Boost](http://www.boost.org/)！ 如果未安装 Boost，则建议使用 Vcpkg 程序包管理器。

1. 按照 [Vcpkg：适用于 Windows 的 C++ 程序包管理器](/cpp/vcpkg)中的说明来安装 vcpkg（如果尚未安装）。

1. 安装 Boost.Test 动态或静态库：

    - 运行 `vcpkg install boost-test` 以安装 Boost.Test 动态库。
    
       - 或 -
       
    - 运行 `vcpkg install boost-test:x86-windows-static` 以安装 Boost.Test 静态库。

1. 运行 `vcpkg integrate install`，使用该库以及 Boost 标头和二进制文件的包含路径配置 Visual Studio。

## <a name="create-a-project-for-your-tests"></a>为测试创建项目

> [!NOTE]
> 在 Visual Studio 2017 版本 15.5 中，没有预配置测试项目或项模板可用于 Boost.Test。 因此，必须创建控制台应用程序项目来存放测试。 计划在 Visual Studio 的未来版本中包含适用于 Boost.Test 的测试模板。

1. 在“解决方案资源管理器”中，右键单击解决方案节点，然后选择“添加”“新建项目...” > 。

1. 在左窗格中，选择“Visual C++” > “Windows 桌面”，然后选择“Windows 控制台应用程序”模板。

1. 为项目提供名称，然后选择“确定”。

## <a name="link-and-configuration-boost-static-library-only"></a>链接和配置（仅限 Boost 静态库）

配置项目以运行 Boost.Test 测试。

1. 若要编辑项目文件，请先将其卸载。 在解决方案资源管理器中，右键单击项目节点，并选择“卸载项目”。 然后，右键单击项目节点并选择“编辑 < 名称\>.vcxproj”。

1. 向“全局”属性组添加两行，如下所示：

    ```xml
    <PropertyGroup Label="Globals">
    ....
        <VcpkgTriplet>x86-windows-static</VcpkgTriplet>
        <VcpkgEnabled>true</VcpkgEnabled>
    </PropertyGroup>
    ```
1. 保存并关闭 \*.vcxproj 文件，然后重新加载该项目。

1. 若要打开“属性页”，右键单击项目节点并选择“属性”。

1. 展开“C/C++” > “代码生成”，然后选择“运行时库”。 为调试静态运行时库选择 `/MTd`，为发布静态运行时库选择 `/MT`。

1. 展开“链接器”>“系统”。 验证“子系统”是否设置为“控制台”。

1. 单击“确定”关闭属性页。

## <a name="add-include-directives"></a>添加 include 指令

1. 如果在测试 .cpp 文件中有 `main` 函数，则将其删除。

1. 在测试 .cpp 文件中，添加任何所需的 `#include` 指令以使程序的类型和函数对测试代码可见。 通常，程序在文件夹层次结构中的上一层。 如果键入 `#include "../"`，则会出现一个 IntelliSense 窗口，使你可以选择头文件的完整路径。

   ![添加 #include 指令](media/cpp-gtest-includes.png "将 include 指令添加到测试 .cpp 文件")

   可以将独立库用于：

   ```cpp
   #include <boost/test/unit_test.hpp>
   ```

   或将单标头版本用于：

   ```cpp
   #include <boost/test/included/unit_test.hpp>
   ```

   然后，定义 `BOOST_TEST_MODULE`。

下面的示例足以使测试可在“测试资源管理器”中被发现：

```cpp
#define BOOST_TEST_MODULE MyTest
#include <boost/test/included/unit_test.hpp\> //single-header
#include "../MyProgram/MyClass.h" // project being tested
#include <string>

BOOST_AUTO_TEST_CASE(my\_boost_test)
{
    std::string expected_value = "Bill";

    // assume MyClass is defined in MyClass.h
    // and get_value() has public accessibility
    MyClass mc;
    BOOST_CHECK(expected_value == mc.get_value());
}
```

## <a name="write-and-run-tests"></a>编写和运行测试
现在已准备就绪，可以编写和运行 Boost Test。 有关测试宏的信息，请参阅 [Boost Test 库文档](http://www.boost.org/doc/libs/1_38_0/libs/test/doc/html/index.html)。 有关使用“测试资源管理器”发现、运行和分组测试的信息，请参阅[使用测试资源管理器运行单元测试](run-unit-tests-with-test-explorer.md)。

## <a name="see-also"></a>请参阅
[编写 C/C++ 单元测试](writing-unit-tests-for-c-cpp.md)
