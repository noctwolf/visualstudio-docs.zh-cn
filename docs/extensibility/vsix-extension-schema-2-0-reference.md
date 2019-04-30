---
title: VSIX 扩展架构 2.0 参考 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- vsix
- extension schema
ms.assetid: 0da81b98-f5e3-40d3-ba9a-94551378d0b4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7cf2840c22bcddb9090cb078be6a8ad53d1ca1aa
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63411129"
---
# <a name="vsix-extension-schema-20-reference"></a>VSIX 扩展架构 2.0 参考
VSIX 部署清单文件描述的 VSIX 包的内容。 由某一架构控制的文件格式。 此架构的 2.0 版支持的自定义类型和属性添加。  清单的架构是可扩展的。 清单加载程序将忽略 XML 元素和属性并不理解。

> [!IMPORTANT]
> Visual Studio 2015 可以加载 Visual Studio 2010、 Visual Studio 2012 或 Visual Studio 2013 格式的 VSIX 文件。

## <a name="package-manifest-schema"></a>包清单架构
 清单 XML 文件的根元素是`<PackageManifest>`。 它具有单个属性`Version`，即清单格式的版本。 如果对格式进行了重大更改，则更改的版本格式。 本指南介绍了清单格式版本 2.0 中，通过设置指定在清单中`Version`属性版本的值 ="2.0"。

### <a name="packagemanifest-element"></a>PackageManifest 元素
 在`<PackageManifest>`根元素，可以使用以下元素：

- `<Metadata>` 元数据和有关包本身的广告信息。 只有一个`Metadata`元素允许在清单中。

- `<Installation>` -本部分将定义可以安装此扩展包，包括可以安装到的应用程序 Sku 的方式。 只有一个`Installation`元素允许在清单中。 必须具有一个清单`Installation`元素或此包不会安装到任何 SKU。

- `<Dependencies>` 的在此处定义一系列可选此包的依赖项。

- `<Assets>` -此部分包含的所有资产包含在此包。 本部分中，没有此包不会呈现任何内容。

- `<AnyElement>*` -清单架构的灵活性以允许任何其他元素。 由清单加载程序无法识别的任何子元素被称为扩展管理器 API 中多余的 XmlElement 对象。 使用这些子元素，VSIX 扩展可以在 Visual Studio 中运行的代码可以访问在运行时在清单文件中定义的其他数据。 请参见 <xref:Microsoft.VisualStudio.ExtensionManager.IExtension.AdditionalElements%2A> 和 <xref:Microsoft.VisualStudio.ExtensionManager.IExtension.LocalizedAdditionalElements%2A>。

### <a name="metadata-element"></a>元数据元素
 本部分是有关包、 其标识和公布信息的元数据。 `<Metadata>` 包含下列元素：

- `<Identity>` -定义此包的标识信息，包括以下属性：

    - `Id` -此属性必须由其作者所选包的唯一 ID。 应的是相同的 CLR 类型是占用命名空间限定的名称：Company.Product.Feature.Name. `Id`特性被限制为 100 个字符。

    - `Version` -定义此包及其内容的版本。 此属性遵循 CLR 程序集版本控制格式：Major.Minor.Build.Revision (1.2.40308.00)。 具有更高版本的版本号的包被视为对包的更新，可以在现有的已安装版本上安装。

    - `Language` -此属性是包的默认语言，对应于此清单中的文本数据。 此属性遵循 CLR 的区域设置代码约定对于资源程序集，例如： en-我们，en，fr-fr 的。 您可以指定`neutral`声明将在 Visual Studio 的任何版本运行的非特定于语言的扩展。 默认值为 `neutral`。

    - `Publisher` -此属性标识此包，公司或单独的名称的发布者。 `Publisher`特性被限制为 100 个字符。

- `<DisplayName>` -此元素指定扩展管理器 UI 中显示的用户友好的包名称。 `DisplayName`内容被限制为 50 个字符。

- `<Description>` -此可选元素是在扩展管理器 UI 中显示的包及其内容的简短说明。 `Description`内容可以包含任何文本的但它具有限制为 1000 个字符。

- `<MoreInfo>` -此可选元素是指向联机包含此包的完整描述的页面的 URL。 协议必须指定为 http。

- `<License>` -此可选元素是包中包含的许可证文件 （.txt、.rtf） 的相对路径。

- `<ReleaseNotes>` -此可选元素是包 （.txt、.rtf），否则显示发行说明的网站的 URL 中包含的发行说明文件的相对路径。

- `<Icon>` -此可选元素是包中包含的图像文件 （png、 bmp、 jpeg、 ico） 的相对路径。 图标图像应为 32 x 32 像素 （或将收缩为该大小），并显示在列表视图 UI。 如果没有`Icon`指定元素，UI 将使用默认值。

- `<PreviewImage>` -此可选元素是包中包含的图像文件 （png、 bmp、 jpeg） 的相对路径。 预览图像应为 200 x 200 像素，显示在 UI 的详细信息。 如果没有`PreviewImage`指定元素，UI 将使用默认值。

- `<Tags>` -此可选元素列出了用于搜索提示的以分号分隔的附加文本标记。 `Tags`元素被限制为 100 个字符。

- `<GettingStartedGuide>` -此可选元素是某一 HTML 文件的相对路径或指向包含有关如何使用扩展或此包中的内容信息的网站的 URL。 本指南将作为安装的一部分启动。

- `<AnyElement>*` -清单架构的灵活性以允许任何其他元素。 清单加载程序不能被识别的任何子元素公开为一系列 XmlElement 对象。 使用这些子元素，VSIX 扩展可以在清单文件中定义的其他数据，并且在运行时枚举它们。

### <a name="installation-element"></a>安装元素
 本部分将定义可在安装此包的方式以及它可以将其安装到的应用程序 Sku。 本部分包含以下属性：

- `Experimental` -设置此属性为 true，如果有当前为所有用户安装的扩展，但正在开发的同一计算机上的更新的版本。 例如，如果您已为所有用户安装 MyExtension 1.0，但想要在同一台计算机上进行调试 MyExtension 2.0，请将实验 ="true"。 此属性是可在 Visual Studio 2015 Update 1 及更高版本。

- `Scope` -此特性可以采用"Global"或"ProductExtension"的值：

    - "全局"，则指定安装不局限于特定的 SKU。 例如，安装扩展 SDK 时，将使用此值。

    - "ProductExtension"指定作用域为单个 Visual Studio Sku 传统 VSIX 扩展 （版本 1.0） 已安装。 这是默认值。

- `AllUsers` -此可选属性指定是否将为所有用户安装此包。 默认情况下，此属性为 false，它指定的包是每个用户。 （当此值设置为 true 时，执行安装的用户必须提升为要安装生成的 VSIX 的管理权限级别。

- `InstalledByMsi` -此可选属性指定是否通过 MSI 安装此包。 通过 MSI 安装的包中安装并托管通过 MSI （程序和功能） 和不通过 Visual Studio Extension Manager。  默认情况下，此属性为 false，它指定不通过 MSI 安装包。

- `SystemComponent` -此可选属性指定是否应考虑此包的系统组件。 系统组件不再显示在扩展管理器 UI 中，不能进行更新。 默认情况下，此属性为 false，它指定包不是系统组件。

- `AnyAttribute*` -`Installation`元素接受将公开在运行时作为名称 / 值对字典的属性的开放式集。

- `<InstallationTarget>` -此元素控制 VSIX 安装程序安装包的位置的位置。 如果的值`Scope`属性是"ProductExtension"包必须为目标的 SKU，已将播发其可用性扩展到其内容的一部分安装的清单文件。 `<InstallationTarget>`元素具有以下属性`Scope`属性具有显式或默认值"ProductExtension":

    - `Id` -此属性标识的包。  该属性如下所示的命名空间约定：Company.Product.Feature.Name. `Id`属性只能包含字母数字字符，并且限制为 100 个字符。 预期值：

        - Microsoft.VisualStudio.IntegratedShell

        - Microsoft.VisualStudio.Pro

        - Microsoft.VisualStudio.Premium

        - Microsoft.VisualStudio.Ultimate

        - Microsoft.VisualStudio.VWDExpress

        - Microsoft.VisualStudio.VPDExpress

        - Microsoft.VisualStudio.VSWinExpress

        - Microsoft.VisualStudio.VSLS

        - My.Shell.App

    - `Version` -此属性指定与此 SKU 的最小值和最大受支持版本的版本范围。 包可以详细介绍它支持的 Sku 的版本。 版本范围表示法是 [10.0-11.0] 其中

        - [-非独占的最低版本。

        - ] 的非独占的最高版本。

        - (-独占的最低版本。

        - ) 的排他的最高版本。

        - 单个版本 #-指定的版本。

        > [!IMPORTANT]
        > 在 Visual Studio 2012 中引入的 VSIX 架构版本 2.0。 若要使用此架构你必须具有 Visual Studio 2012 或更高版本在计算机上安装并使用是该产品的一部分 VSIXInstaller.exe。 你可以面向早期版本的 Visual Studio 与 Visual Studio 2012 或更高版本 vsixinstaller 找，但只能通过使用更高版本的安装程序。

        请参阅 visual Studio 2017 版本号[Visual Studio 生成号和发布日期](../install/visual-studio-build-numbers-and-release-dates.md)。

        当表示 Visual Studio 2017 版本的版本，应始终为次要版本**0**。 例如，Visual Studio 2017 版本 15.3.26730.0 应表示为 [15.0.26730.0,16.0)。 这只是所需的 Visual Studio 2017 和更高版本的版本号。

    - `AnyAttribute*` -`<InstallationTarget>`元素允许开放式集的属性公开在运行时作为名称 / 值对字典。

### <a name="dependencies-element"></a>依赖关系元素
 此元素包含此包声明的依赖项的列表。 如果指定了任何依赖项，这些包 (由标识其`Id`) 必须之前已安装。

- `<Dependency>` 元素的此子元素具有以下属性：

    - `Id` -此属性必须为依赖的包的唯一 ID。 此标识值必须匹配`<Metadata><Identity>Id`此包所依赖的包的属性。 `Id`属性遵循命名空间约定：Company.Product.Feature.Name. 属性只能包含字母数字字符，并且限制为 100 个字符。

    - `Version` -此属性指定与此 SKU 的最小值和最大受支持版本的版本范围。 包可以详细介绍它支持的 Sku 的版本。 版本范围表示法是 [12.0，13.0]，其中：

        - [-非独占的最低版本。

        - ] 的非独占的最高版本。

        - (-独占的最低版本。

        - ) 的排他的最高版本。

        - 单个版本 #-指定的版本。

    - `DisplayName` -此属性是包的依赖，如对话框和错误消息的 UI 元素中使用的显示名称。 该属性是可选的除非通过 MSI 安装从属包。

    - `Location` -此可选属性指定是嵌套的 VSIX 包到此 VSIX 中的相对路径或指向的依赖项的下载位置的 URL。 此属性用于帮助用户找到必备组件包。

    - `AnyAttribute*` -`Dependency`元素接受将公开在运行时作为名称 / 值对字典的属性的开放式集。

### <a name="assets-element"></a>资产元素
 此元素包含一系列`<Asset>`扩展或内容的每个元素的标记显示此包。

- `<Asset>` -此元素包含以下属性和元素：

  - `Type` 扩展或此元素所表示的内容的类型。 每个`<Asset>`元素必须具有单个`Type`，但多个`<Asset>`元素可能具有相同`Type`。 根据命名空间约定，应为完全限定名称，表示此属性。 已知的类型包括：

    1. Microsoft.VisualStudio.VsPackage

    2. Microsoft.VisualStudio.MefComponent

    3. Microsoft.VisualStudio.ToolboxControl

    4. Microsoft.VisualStudio.Samples

    5. Microsoft.VisualStudio.ProjectTemplate

    6. Microsoft.VisualStudio.ItemTemplate

    7. Microsoft.VisualStudio.Assembly

       可以创建自己的类型，并为其提供唯一名称。 在 Visual Studio 内部的运行时，你的代码可枚举并通过扩展管理器 API 访问这些自定义的类型。

  - `Path` -包含资产的包中文件夹的文件的相对路径。

  - `TargetVersion` -给定的资产适用的版本范围。 用于传送到不同版本的 Visual Studio 资产的多个版本。 需要 Visual Studio 2017.3 或更高版本才能生效。

  - `AnyAttribute*` 的在运行时作为名称 / 值对字典的路由公开的属性开放式集。

     `<AnyElement>*` 的之间允许任何结构化的内容`<Asset>`开始和结束标记。 所有元素都公开为一系列 XmlElement 对象。 VSIX 扩展可以在清单文件中定义结构化的类型特定的元数据，并且在运行时枚举它们。

### <a name="sample-manifest"></a>示例清单

```
<?xml version="1.0" encoding="utf-8"?>
<PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011" xmlns:d="http://schemas.microsoft.com/developer/vsx-schema-design/2011">
  <Metadata>
    <Identity Id="0000000-0000-0000-0000-000000000000" Version="1.0" Language="en-US" Publisher="Company" />
    <DisplayName>Test Package</DisplayName>
    <Description>Information about my package</Description>
    <MoreInfo>http://www.fabrikam.com/Extension1/</MoreInfo>
    <License>eula.rtf</License>
    <ReleaseNotes>notes.txt</ReleaseNotes>
    <Icon>Images\icon.png</Icon>
    <PreviewImage>Images\preview.png</PreviewImage>
  </Metadata>
  <Installation InstalledByMsi="false" AllUsers="false" SystemComponent="false" Scope="ProductExtension">
    <InstallationTarget Id="Microsoft.VisualStudio.Pro" Version="[11.0, 12.0]" />
  </Installation>
  <Dependencies>
    <Dependency Id="Microsoft.Framework.NDP" DisplayName="Microsoft .NET Framework" d:Source="Manual" Version="[4.5,)" />
    <Dependency Id="Microsoft.VisualStudio.MPF.12.0" DisplayName="Visual Studio MPF 12.0" d:Source="Installed" Version="[12.0]" />
  </Dependencies>
  <Assets>
    <Asset Type="Microsoft.VisualStudio.VsPackage" d:Source="Project" d:ProjectName="%CurrentProject%" Path="|%CurrentProject%;PkgdefProjectOutputGroup|" />
  </Assets>
</PackageManifest>
```

## <a name="see-also"></a>请参阅
- [传送 Visual Studio 扩展](../extensibility/shipping-visual-studio-extensions.md)
