---
title: 如何：创建。Vsct 文件 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, creating
ms.assetid: b955f51c-f9f9-49c3-a8e4-63b6eb0e0341
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d8dd2e677cae2e54a8dff716aef72f1d6abc6b40
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602801"
---
# <a name="how-to-create-a-vsct-file"></a>如何：创建.vsct 文件

有几种方法来创建基于 XML 的 Visual Studio 命令表配置 (*.vsct*) 文件。

- 您可以创建新的 VSPackage 中[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]包模板。

- 可以使用基于 XML 的命令表配置编译器*Vsct.exe*，以便生成一个文件从现有 *.ctc*文件。

- 可以使用*Vsct.exe*生成 *.vsct*文件从现有 *.cto*文件。

- 您可以手动创建一个新 *.vsct*文件。

  本文介绍如何手动创建一个新 *.vsct*文件。

### <a name="to-manually-create-a-new-vsct-file"></a>若要手动创建新的.vsct 文件

1. 启动 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。

2. 上**文件**菜单，依次指向**新建**，然后单击**文件**。

3. 在中**模板**窗格中，单击**XML 文件**，然后单击**打开**。

4. 上**视图**菜单上，单击**属性**显示 XML 文件的属性。

5. 在中**属性**窗口中，单击**浏览**按钮**架构**属性。

6. 在 XSD 架构的列表中选择*vsct.xsd*架构。 如果不是在列表中，单击**添加**，然后找到本地驱动器上的文件。 单击**确定**完成之后。

7. 在 XML 文件中，键入 *< CommandTable* ，然后按**选项卡**。通过键入结束标记*>*。

    此操作将创建一个基本 *.vsct*文件。

8. 填写想要添加的 XML 文件的元素，根据[VSCT XML 架构参考](../../extensibility/vsct-xml-schema-reference.md)。 有关详细信息，请参阅[创作.vsct 文件](../../extensibility/internals/authoring-dot-vsct-files.md)

<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-ctc-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-ctc-file"></a>如何：从现有的.ctc 文件创建.vsct 文件

您可以创建基于 XML 的 *.vsct*文件从现有命令表 *.ctc*源文件。 通过执行此操作，可以利用基于 XML 的新 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 命令表 (VSCT) 编译器格式。

### <a name="to-create-a-vsct-file-from-a-ctc-file"></a>从 .ctc 文件创建 .vsct  文件

1. 获取 Perl 语言的副本。

2. 获取 Perl 脚本的副本*ConvertCTCToVSCT.pl*，它通常位于 *\<Visual Studio SDK 安装路径 > \VisualStudioIntegration\Tools\bin*文件夹。

3. 获取一份 *.ctc*你想要转换的源文件。

4. 将这些文件放在同一个目录中。

5. 在[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]命令提示窗口中，导航到的目录。

6. 类型

   ```
   perl.exe ConvertCTCtoVSCT.pl PkgCmd.ctc PkgCmd.vsct
   ```

    其中*PkgCmd.ctc*的名称 *.ctc*文件并*PkgCmd.vsct*的名称 *.vsct*你想要创建的文件。

    此操作将创建一个新 *.vsct* XML 命令表源文件。 可以使用编译此文件*Vsct.exe*，使用 VSCT 编译器为您像对任何其他 *.vsct*文件。

   > [!NOTE]
   >  可以改进的可读性 *.vsct*通过重新格式化 XML 注释的文件。

<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-cto-file"></a>如何：从现有.cto 文件创建.vsct 文件

您可以创建基于 XML 的 *.vsct*从现有的二进制文件的文件 *.cto*文件。 这样既可充分利用新的命令表编译器格式。 此过程的工作原理，即使 *.cto*从编译文件 *.ctc*文件。 可以编辑和编译 *.vsct*到其他.cto 文件的文件。

### <a name="to-create-a-vsct-file-from-a-cto-file"></a>从 .cto 文件创建 .Vsct 文件

1.  获取的副本 *.cto*文件和其对应 *.ctsym*文件。

2.  将文件放到与相同的目录*vsct.exe*编译器。

3.  在 Visual Studio 命令提示符处，转到包含的目录 *.cto*并 *.ctsym*文件。

4.  类型

    ```
    vsct.exe <ctofilename>.cto <vsctfilename>.vsct -S<symfilename>.ctsym
    ```

     其中\<ctofilename\>的名称 *.cto*文件中， \<vsctfilename\>的名称 *.vsct*文件您想要创建和\<symfilename\>的名称 *.ctsym*文件。

     此过程将创建一个新 *.vsct* XML 命令表编译器文件。 可以编辑和编译的文件*vsct.exe*，使用 vsct 编译器为您像对任何其他 *.vsct*文件。

## <a name="compile-the-code"></a>编译代码
 只需添加 *.vsct*到项目文件不会导致编译它。 必须在生成过程中将其合并。

### <a name="to-add-a-vsct-file-to-project-compilation"></a>若要将.vsct 文件添加到项目编译

1.  在编辑器中打开项目文件。 如果加载该项目，必须先卸载它。

2.  添加[ItemGroup 元素](../../msbuild/itemgroup-element-msbuild.md)，其中包含`VSCTCompile`元素，如下面的示例中所示。

    ```xml
    <ItemGroup>
      <VSCTCompile Include="TopLevelMenu.vsct">
        <ResourceName>Menus.ctmenu</ResourceName>
      </VSCTCompile>
    </ItemGroup>

    ```

     `ResourceName`元素应始终设置为`Menus.ctmenu`。

3.  如果您的项目包含 *.resx*文件中，添加`EmbeddedResource`元素，其中包含`MergeWithCTO`元素，如下面的示例中所示：

    ```xml
    <EmbeddedResource Include="VSPackage.resx">
      <MergeWithCTO>true</MergeWithCTO>
      <ManifestResourceName>VSPackage</ManifestResourceName>
    </EmbeddedResource>

    ```

     此标记应发送到内部`ItemGroup`包含嵌入的资源的元素。

4.  打开包文件，通常名为 *\<ProjectName\>Package.cs*或 *\<ProjectName\>Package.vb*，在编辑器中。

5.  添加`ProvideMenuResource`属性包类，如下面的示例中所示。

    ```csharp
    [ProvideMenuResource("Menus.ctmenu", 1)]
    ```

     第一个参数值必须匹配的值的`ResourceName`在项目文件中定义的属性。

## <a name="see-also"></a>请参阅
- [创作.vsct 文件](../../extensibility/internals/authoring-dot-vsct-files.md)
- [Visual Studio 命令表格 (.vsct) 文件](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [VSCT XML 架构参考](../../extensibility/vsct-xml-schema-reference.md)