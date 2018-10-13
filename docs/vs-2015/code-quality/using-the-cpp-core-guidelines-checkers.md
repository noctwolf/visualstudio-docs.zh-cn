---
title: 使用 c + + Core Guidelines 检查器 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2098fd9-8334-4e95-9b8d-bc3da689d9e3
caps.latest.revision: 11
author: corob-msft
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2fc975ab5c9c1e43b79ddd861bca3a61e9005f5f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49194085"
---
# <a name="using-the-c-core-guidelines-checkers"></a>使用 c + + Core Guidelines 检查器
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

C + + Core Guidelines 了一可移植的指导原则、 规则和有关在 c + + 创建的 c + + 专家和设计器中编写代码的最佳做法。  Visual Studio 现在支持外接程序的包创建其他规则的代码分析工具来检查您的代码与 c + + Core Guidelines 的符合性并提出改进建议。  
  
## <a name="the-c-core-guidelines-project"></a>C + + 核心准则项目  
 C + + Core Guidelines 由 Bjarne Stroustrup 和其他人创建的它是如何安全有效地使用现代 c + + 的指南。 指南强调了静态类型安全性和资源安全。 他们确定消除或最小化的语言，最容易出错的各个部分的方法，并建议如何使代码更简单和更高的性能可靠的方式。 由标准 c + + 基础维护这些指导原则。 若要了解详细信息，请参阅本文档中， [c + + Core Guidelines](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)，并在访问 c + + Core Guidelines 文档项目文件[GitHub](https://github.com/isocpp/CppCoreGuidelines)。  
  
 Microsoft 通过使 c + + Core Check 代码分析规则集，您可以通过使用 Nuget 包添加到你的项目支持的 c + + Core Guidelines 工作量。 应用程序包名为 Microsoft.CppCoreCheck，并可通过[ http://www.nuget.org/packages/Microsoft.CppCoreCheck ](http://www.nuget.org/packages/Microsoft.CppCoreCheck)。 此软件包要求必须至少安装 Visual Studio 2015 Update 1。  
  
 包还将作为依赖项，仅限标头的准则支持库 (GSL) 安装另一个包。 GSL，还可以在 GitHub 上[ https://github.com/Microsoft/GSL ](https://github.com/Microsoft/GSL)。  
  
## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>启用代码分析中的 c + + Core Check 准则  
 若要启用 c + + Core Check 代码分析工具，请 Microsoft.CppCoreCheck NuGet 包安装到你想要在 Visual Studio 中检查每个 c + + 项目上。  
  
#### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project"></a>若要将 Microsoft.CppCoreCheck 包添加到你的项目  
  
1.  在中**解决方案资源管理器**，右键单击以在你想要添加到包的解决方案中打开你的项目的上下文菜单。 选择**管理 NuGet 包**以打开**NuGet 包管理器**。  
  
2.  在中**NuGet 包管理器**窗口中，搜索 Microsoft.CppCoreCheck。  
  
     ![Nuget 包管理器窗口中显示了 CppCoreCheck 包](../code-quality/media/cppcorecheck-nuget-window.PNG "CPPCoreCheck_Nuget_Window")  
  
3.  选择 Microsoft.CppCoreCheck 包，然后选择**安装**按钮将规则添加到你的项目。  
  
 NuGet 包将其他 MSBuild.targets 文件添加到项目中，这些项目上启用代码分析时调用。 此.targets 文件将作为其他扩展的 c + + Core Check 规则添加到 Visual Studio 代码分析工具。  
  
 可以通过选择您的项目中启用代码分析**生成时启用代码分析**中的复选框**代码分析**一部分**属性页**对话框你的项目。  
  
 ![代码分析常规设置的属性页](../code-quality/media/cppcorecheck-codeanalysis-general.png "CPPCoreCheck_CodeAnalysis_General")  
  
 C + + Core Check 规则成为运行时启用代码分析的默认规则集的一部分。 由于 c + + Core Check 规则是在开发下，某些规则可能不是可用于所有代码，但在开发过程中可能是信息性。 这些规则会释放为实验性。 您可以选择是否要为你的项目属性中运行的已发布或实验性的规则。  
  
 ![代码分析扩展设置的属性页](../code-quality/media/cppcorecheck-codeanalysis-extensions.png "CPPCoreCheck_CodeAnalysis_Extensions")  
  
 若要启用或禁用 c + + Core Check 规则集，请打开**属性页**对话框为您的项目。 下**配置属性**，展开**代码分析**，**扩展**。 在下拉列表中来控制旁边**启用 c + + Core Check （已发布）** 或**启用 c + + Core Check （实验性）**，选择**是**或者**否**。 选择**确定**或**应用**以保存所做的更改。  
  
## <a name="check-types-bounds-and-lifetimes"></a>检查类型、 边界和生存期  
 C + + Core Check 包当前包含的检查器，即[类型安全](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#SS-type)，[界限安全](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#SS-bounds)，并[生存期安全](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#SS-lifetime)配置文件。  
  
 下面是类的 c + + Core Check 规则可发现的问题的一个示例：  
  
```cpp  
// CoreCheckExample.cpp  
// Add CppCoreCheck package and enable code analysis in build for warnings.  
  
int main()  
{  
    int arr[10];           // warning C26494  
    int* p = arr;          // warning C26485  
  
    [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1  
    {  
        int* q = p + 1;    // warning C26481 (suppressed)  
        p = q++;           // warning C26481 (suppressed)  
    }  
  
    return 0;  
}  
```  
  
 此示例演示了几个 c + + Core Check 规则可以找到的警告：  
  
-   C26494 是规则 Type.5： 始终初始化对象。  
  
-   C26485 是规则 Bounds.3： 没有数组指针的衰减。  
  
-   C26481 是规则 Bounds.1： 请勿使用指针算法。 请改用 `span`。  
  
 如果安装并启用时编译此代码前, 两个警告是输出，但禁止第三个 c + + Core Check 代码分析规则集。 下面是示例代码的生成输出：  
  
 **1 >---启动生成： 项目： CoreCheckExample、 配置： Debug Win32-**  
**----**  
**1 > CoreCheckExample.cpp**  
**1 > CoreCheckExample.vcxproj-> C:\Users\username\documents\visual studio 2015\P**  
**rojects\CoreCheckExample\Debug\CoreCheckExample.exe**  
**1 > CoreCheckExample.vcxproj-> C:\Users\username\documents\visual studio 2015\P**  
**rojects\CoreCheckExample\Debug\CoreCheckExample.pdb (完整 PDB)**  
**c:\users\username\documents\visual studio 2015\projects\corecheckexample\coreche**  
**ckexample\corecheckexample.cpp(6)： 警告 C26494： 变量 arr 是 uninitializ**  
**ed.始终初始化对象。(type.5: http://go.microsoft.com/fwlink/p/?Link**  
**ID = 620421)**  
**c:\users\username\documents\visual studio 2015\projects\corecheckexample\coreche**  
**ckexample\corecheckexample.cpp(7)： 警告 C26485： 表达式 arr： 组到**  
 **指针的衰减。(bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)**  
**=== 生成： 1 个成功，0 失败，0 最新，0 已跳过 ===** c + + Core Guidelines 的目的是为了帮助您编写更好、 更安全代码。 但是，如果有一个规则或配置文件不应应用的实例时，很容易在代码中直接取消。 可以使用`gsl::suppress`属性以防止 c + + Core Check 检测和报告任何违反了下面的代码块中的规则。 可以将标记单个语句，若要禁止显示特定的规则。 甚至可以禁止整个绑定配置文件，方法是编写`[[gsl::suppress(bounds)]]`而不包括特定的规则数。  
  
## <a name="use-the-guideline-support-library"></a>使用准则支持库  
 Microsoft.CppCoreCheck NuGet 包还会安装包包含 Microsoft 实现的准则支持库 (GSL)。 GSL 也会出现在独立的窗体，请[ http://www.nuget.org/packages/Microsoft.Gsl ](http://www.nuget.org/packages/Microsoft.Gsl)。 此库很有帮助，如果你想要遵循的核心准则。 GSL 包括使您易出错的构造替换为更安全的替代方法的定义。 例如，您可以替换`T*, length`对参数使用`span<T>`类型。 GSL 开放源代码，因此如果你想要看一看库源注释，或提供，该项目，请参阅[ https://github.com/Microsoft/GSL ](https://github.com/Microsoft/GSL)。



