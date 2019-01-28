---
title: Visual Studio 2017 扩展中的重大更改 |Microsoft Docs
ms.date: 11/09/2016
ms.topic: conceptual
ms.assetid: 54d5af60-0b44-4ae1-aa57-45aa03f89f3d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8a862d3da21d082c65e742bdd69851121f5b463e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55012265"
---
# <a name="changes-in-visual-studio-2017-extensibility"></a>Visual Studio 2017 扩展中的更改

使用 Visual Studio 2017，我们提供[更快、 轻量的 Visual Studio 安装体验](https://blogs.msdn.microsoft.com/visualstudio/2016/04/01/faster-leaner-visual-studio-installer)可在用户系统上的 Visual Studio 的影响减小时向用户提供更好的选择对工作负荷和功能安装。 若要支持这些改进，我们对扩展性模型，进行了更改，并对 Visual Studio 扩展性做出一些重大更改。 此文档将描述这些更改，并且可以做什么解决它们的技术详细信息。 请注意，某些信息是在时间点实现的详细信息，可能会更高版本发生更改。

## <a name="changes-affecting-vsix-format-and-installation"></a>更改影响的 VSIX 格式和安装

我们将引入 VSIX v3 （版本 3） 格式，以支持的轻量级安装体验。

对 VSIX 格式的更改包括：

* 安装程序先决条件的声明。 提供了一种轻型，快速安装 Visual Studio 中，安装程序将立即向用户提供更多配置选项。 因此，若要确保安装的功能和组件所需的扩展，扩展将需要声明及其依赖项。
  * Visual Studio 2017 安装程序将自动提供的用于获取和安装用户所必需的组件的过程中安装您的扩展插件。
  * 尝试安装未生成使用新的 VSIX v3 格式，即使它们已标记为面向版本 15.0 其清单中的扩展时，还会警告用户。
* VSIX 格式的增强的功能。 在传递[影响较小的安装](https://blogs.msdn.microsoft.com/visualstudio/2016/04/25/anatomy-of-a-low-impact-visual-studio-install)还支持通过并行安装的 Visual studio，我们不再将最多的配置数据保存到系统注册表并已从 gac 中的 Visual Studio-特定于程序集。 我们还增加了 VSIX 格式和 VSIX 安装引擎的功能，您可以使用它而不是 MSI 或 EXE 安装你对某些类型的安装的扩展。

  新功能包括：

  * 注册到指定的 Visual Studio 实例。
  * 安装之外[扩展文件夹](set-install-root.md)。
  * 检测的处理器体系结构。
  * 分隔语言的语言包的依赖关系。
  * 与安装[NGEN 支持](ngen-support.md)。

## <a name="building-an-extension-for-visual-studio-2017"></a>Visual Studio 2017 生成扩展

设计器工具用于创作新的 VSIX v3 清单格式现已推出 Visual Studio 2017。 请参阅随附的文档[如何：将扩展性项目迁移到 Visual Studio 2017](how-to-migrate-extensibility-projects-to-visual-studio-2017.md)有关使用设计器工具或对项目进行手动更新的详细信息和清单以开发 VSIX v3 扩展。

## <a name="change-visual-studio-user-data-path"></a>更改：Visual Studio 用户数据路径

以前，只能安装一个每个主要版本的 Visual Studio 可能存在每台计算机上。 若要支持的 Visual Studio 2017 的并行安装，用户的计算机上可能存在的 Visual Studio 的多个用户数据路径。

在 Visual Studio 进程内运行的代码应更新为使用 Visual Studio 设置管理器。 Visual Studio 进程外部运行的代码可以查找特定的 Visual Studio 安装的用户路径[按照此处的指南](locating-visual-studio.md)。

## <a name="change-global-assembly-cache-gac"></a>更改：全局程序集缓存 (GAC)

大多数 Visual Studio 核心程序集不能再安装到 GAC 中。 以便在 Visual Studio 进程中运行的代码仍可以在运行时找到所需程序集进行以下更改。

> [!NOTE]
> [INSTALLDIR] 下面指的是 Visual Studio 的安装根目录。 *VSIXInstaller.exe*将自动填充此操作，但若要编写自定义部署代码，请阅读[查找 Visual Studio](locating-visual-studio.md)。

* 仅安装到 GAC 的程序集：
  * 现在，这些程序集都安装了下<em>[INSTALLDIR] \Common7\IDE\*，* [INSTALLDIR] \Common7\IDE\PublicAssemblies</em>或 *[INSTALLDIR] \Common7\IDE\PrivateAssemblies*。 这些文件夹是 Visual Studio 进程的探测路径的一部分。

* 已安装到非探测路径和 GAC 的程序集：
  * 在 GAC 中的副本已从安装程序删除。
  * 一个 *.pkgdef*添加了文件，以指定程序集的代码基础项。

    例如：

    ```xml
    [$RootKey$\RuntimeConfiguration\dependentAssembly\codeBase\{UniqueGUID}]
    "name"="AssemblyName" "codeBase"="$PackageFolder$\AssemblyName.dll"
    "publicKeyToken"="Public Key Token"
    "culture"="neutral"
    "version"=15.0.0.0
    ```
    在运行时，Visual Studio pkgdef 子系统将这些将项合并到 Visual Studio 进程的运行时配置文件 (在 *[VSAPPDATA]\devenv.exe.config*) 作为[ `<codeBase>` ](/dotnet/framework/configure-apps/file-schema/runtime/codebase-element)元素。 这是让 Visual Studio 进程查找您的程序集，因为它可以避免通过探测路径搜索的建议的方法。

### <a name="reacting-to-this-breaking-change"></a>对此项重大更改做出反应

* 如果您的扩展插件在 Visual Studio 进程中运行：
  * 你的代码将能够找到 Visual Studio 核心程序集。
  * 请考虑使用 *.pkgdef*文件可以根据需要指定您的程序集的路径。
* 如果在 Visual Studio 进程之外运行您的扩展插件：
  * 查找 Visual Studio 核心程序集下，请考虑<em>[INSTALLDIR] \Common7\IDE\*，* [INSTALLDIR] \Common7\IDE\PublicAssemblies</em>或 *[INSTALLDIR] \Common7\IDE\PrivateAssemblies*使用配置文件或程序集冲突解决程序。

## <a name="change-reduce-registry-impact"></a>更改：降低注册表的影响

### <a name="global-com-registration"></a>全局 COM 注册

* 以前，Visual Studio 安装到 HKEY_CLASSES_ROOT 和 HKEY_LOCAL_MACHINE 配置单元，以支持本机 COM 注册多个注册表项。 若要消除这种影响，Visual Studio 现在将使用[COM 组件免注册激活](https://msdn.microsoft.com/library/ms973913.aspx)。
* 因此，大多数 TLB / OLB / Visual studio 默认情况下不再安装在 %programfiles (x86) %\Common Files\Microsoft Shared\MSEnv DLL 文件。 这些文件现在安装下 [INSTALLDIR] 使用 Visual Studio 主机进程使用的相应免注册 COM 清单。
* 因此，依赖于全局 Visual Studio COM 接口的 COM 注册的外部代码将无法再找到这些注册。 在 Visual Studio 进程内运行的代码不会看到差异。

### <a name="visual-studio-registry"></a>Visual Studio 注册表

* 以前，Visual Studio 都安装到系统的多个注册表项**HKEY_LOCAL_MACHINE**并**HKEY_CURRENT_USER** -特定于 Visual Studio 项下的配置单元：
  * **HKLM\Software\Microsoft\VisualStudio\{版本}**:创建 MSI 安装程序和每个计算机上的扩展的注册表项。
  * **HKCU\Software\Microsoft\VisualStudio\{版本}**:创建 Visual Studio 来存储特定于用户的设置的注册表项。
  * **HKCU\Software\Microsoft\VisualStudio\{版本} _Config**:Visual Studio HKLM 密钥更高版本，加上的注册表项的副本从合并 *.pkgdef*扩展插件的文件。
* 若要减少对注册表的影响，Visual Studio 现在将使用[RegLoadAppKey](/windows/desktop/api/winreg/nf-winreg-regloadappkeya)函数来将注册表项存储在专用二进制文件下 *[VSAPPDATA]\privateregistry.bin*。 只有极少数的 Visual Studio 特定的密钥保留在系统注册表中。

* 在 Visual Studio 进程内运行的现有代码不会受到影响。 Visual Studio 将重定向到专用注册表 HKCU-特定于 Visual Studio 项下的所有注册表操作。 读取和写入注册表的其他位置将继续使用系统注册表。
* 外部代码需要加载并从 Visual Studio 注册表项的此文件中读取。

### <a name="reacting-to-this-breaking-change"></a>对此项重大更改做出反应

* 外部代码应将转换为的 COM 组件以及使用免注册激活。
* 外部组件可以找到 Visual Studio 位置[按照此处的指南](https://blogs.msdn.microsoft.com/heaths/2016/09/15/changes-to-visual-studio-15-setup)。
* 我们建议使用外部组件[外部设置管理器](/dotnet/api/microsoft.visualstudio.settings.externalsettingsmanager)而不是直接向 Visual Studio 的注册表项读取/写入。
* 检查是否可能已使用您的扩展插件的组件实现注册的另一种方法。 例如，可能能够利用新的调试器扩展[msvsmon JSON 文件 COM 注册](migrate-debugger-COM-registration.md)。
