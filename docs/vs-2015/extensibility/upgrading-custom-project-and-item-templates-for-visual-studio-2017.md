---
title: 升级 Visual studio"15"的自定义项目和项模板 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad02477b-e101-4f32-aeb7-292bf95d5c2f
caps.latest.revision: 4
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 31e2edc444e81bbfb23cc70c542c0c7ee8ab8997
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51760256"
---
# <a name="upgrading-custom-project-and-item-templates-for-visual-studio-15"></a>升级 Visual studio"15"的自定义项目和项模板
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

从 Visual Studio"15"预览版 4 中，Visual Studio 正在改变其发现由.vsix 或.msi 安装的项目和项模板的方式。 如果你拥有使用自定义项目或项模板的扩展，您需要更新你的扩展。 本主题介绍你必须执行的操作。  
  
 此更改会影响仅 Visual Studio"15"。 它不会影响 Visual Studio 的早期版本。  
  
 如果你想要创建项目或项模板作为 VSIX 扩展的一部分，请参阅[创建自定义项目和项模板](../extensibility/creating-custom-project-and-item-templates.md)。  
  
## <a name="template-scanning"></a>扫描的模板  
 以前， **devenv /setup**或**devenv /installvstemplates**扫描以查找项目和项模板的本地磁盘。 从预览版 4 中，扫描将在执行仅对于用户级别位置 (**%USERPROFILE%\Documents\\< Visual Studio 版本\>\My Exported Templates\\**) 中所用的生成的模板**文件 / 导出模板**命令。  
  
 对于其他 （非用户） 的位置，您必须包含指定的位置和模板的其他特征的 manifest(.vstman) 文件。 适用于模板的.vstemplate 文件以及生成.vstman 文件。 如果您安装使用.vsix 扩展，可以通过重新编译 Visual Studio"15"预览版 2 中的扩展来实现此目的。 但如果您使用一个.msi，则需要手动进行的更改。 您需要执行的操作进行这些更改的列表，请参阅**对扩展安装与升级。MSI**本主题中更高版本。  
  
## <a name="how-to-update-a-vsix-extension-with-project-or-item-templates"></a>如何使用项目或项模板更新 VSIX 扩展  
 此过程说明如何通过 Visual Studio"15"预览版 2 更新现有的 VSIX 扩展。  
  
1.  在 Visual Studio"15"预览版 2 中打开该解决方案。 你将需要升级的代码。 单击 **“确定”**。  
  
2.  在升级完成后，你可能需要更改安装目标版本。 在 VSIX 项目中，打开 source.extension.vsixmanifest 文件，然后选择**安装目标**选项卡。如果**版本范围**字段是 **[14.0]**，单击**编辑**并将其更改为包括 Visual Studio"15"。 例如，您可以将其设置为 **[14.0,15.0]** 到 Visual Studio 2015 或 Visual Studio"15"，或安装扩展 **[15.0]** 以将其安装到仅 Visual Studio"15"。  
  
3.  重新编译代码。  
  
4.  关闭 Visual Studio。  
  
5.  安装 VSIX。  
  
6.  可以通过执行以下操作来测试更新：  
  
    1.  扫描更改的文件被激活由以下注册表项：  
  
         **reg 添加 hklm\software\microsoft\visualstudio\15.0\VSTemplate /v DisableTemplateScanning /t REG_DWORD /d 1 /reg:32**  
  
    2.  添加密钥后，运行**devenv /installvstemplates**。  
  
    3.  重新打开 Visual Studio。 应该在预期位置中找到你的模板。  
  
    > [!NOTE]
    >  存在注册表项时，Visual Studio 扩展性项目模板不可用。 必须删除注册表项 (和重新运行**devenv /installvstemplates**) 来使用它们。  
  
## <a name="other-recommendations-for-deploying-project-and-item-templates"></a>部署项目和项模板的其他建议  
  
-   避免使用压缩的模板文件。 压缩需要不会进行压缩以便检索资源和内容文件的模板，因此它们将考虑使用。 相反，应将项目和项模板部署为单个文件，以加快模板初始化其自身目录下。 VSIX 扩展的 SDK 生成任务会自动将任何压缩的模板解压缩创建 VSIX 文件时。  
  
-   避免以避免不必要的资源程序集加载模板在发现期间使用的模板名称、 说明、 图标或预览包/资源 ID 条目。 相反，本地化的清单可用于创建每个区域设置，它使用本地化的名称或属性的模板条目。  
  
-   如果要包含为文件项模板，清单生成可能无法让你预期的结果。 在这种情况下，你将需要向 VSIX 项目添加手动生成清单。  
  
## <a name="file-changes-in-project-and-item-templates"></a>项目和项模板中的文件更改  
 我们将显示 Visual Studio 2015 版本和模板文件的 Visual Studio"15"版本之间的差异的点，以便可以正确地创建新文件。  
  
 下面是 Visual Studio 2015 创建的默认项目.vstemplate 文件：  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Project" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:sdk="http://schemas.microsoft.com/developer/vstemplate-sdkextension/2010">  
  <TemplateData>  
    <Name>ProjectTemplate1</Name>  
    <Description>ProjectTemplate1</Description>  
    <Icon>ProjectTemplate1.ico</Icon>  
    <ProjectType>CSharp</ProjectType>  
    <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
    <SortOrder>1000</SortOrder>  
    <TemplateID>05b79cc9-2146-4716-a8e5-7e085cdd2221</TemplateID>  
    <CreateNewFolder>true</CreateNewFolder>  
    <DefaultName>ProjectTemplate1</DefaultName>  
    <ProvideDefaultName>true</ProvideDefaultName>  
  </TemplateData>  
  <TemplateContent>  
    <Project File="ProjectTemplate.csproj" ReplaceParameters="true">  
      <ProjectItem ReplaceParameters="true" TargetFileName="Properties\AssemblyInfo.cs">AssemblyInfo.cs</ProjectItem>  
      <ProjectItem ReplaceParameters="true" OpenInEditor="true">Class1.cs</ProjectItem>  
    </Project>  
  </TemplateContent>  
</VSTemplate>  
  
```  
  
 下面是从重新生成的 VSIX 项目生成.vstman 文件 （可以在 VSIX 项目的清单目录中找到它）：  
  
```  
VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Project">  
    <RelativePathOnDisk>CSharp\1033\ProjectTemplate1</RelativePathOnDisk>  
    <TemplateFileName>ProjectTemplate1.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>ProjectTemplate1</Name>  
        <Description>ProjectTemplate1</Description>  
        <Icon>ProjectTemplate1.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <SortOrder>1000</SortOrder>  
        <TemplateID>05b79cc9-2146-4716-a8e5-7e085cdd2221</TemplateID>  
        <CreateNewFolder>true</CreateNewFolder>  
        <DefaultName>ProjectTemplate1</DefaultName>  
        <ProvideDefaultName>true</ProvideDefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```  
  
 提供的信息[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)元素保持不变。 **\<VSTemplateContainer >** 元素指向关联的模板的.vstemplate 文件。  
  
 下面是由 Visual Studio 2015 创建的默认项.vstemplate 文件：  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:sdk="http://schemas.microsoft.com/developer/vstemplate-sdkextension/2010">  
  <TemplateData>  
    <Name>ItemTemplate1</Name>  
    <Description>ItemTemplate1</Description>  
    <Icon>ItemTemplate1.ico</Icon>  
    <TemplateID>bfeadf8e-a251-4109-b605-516b88e38c8d</TemplateID>  
    <ProjectType>CSharp</ProjectType>  
    <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
    <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
    <DefaultName>Class.cs</DefaultName>  
  </TemplateData>  
  <TemplateContent>  
    <References>  
      <Reference>  
        <Assembly>System</Assembly>  
      </Reference>  
    </References>  
    <ProjectItem ReplaceParameters="true">Class.cs</ProjectItem>  
  </TemplateContent>  
</VSTemplate>  
  
```  
  
 下面是从重新生成的 VSIX 项目生成.vstman 文件 （可以在 VSIX 项目的清单目录中找到它）：  
  
```  
VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Item">  
    <RelativePathOnDisk>CSharp\1033\ItemTemplate1</RelativePathOnDisk>  
    <TemplateFileName>ItemTemplate1.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>ItemTemplate1</Name>  
        <Description>ItemTemplate1</Description>  
        <Icon>ItemTemplate1.ico</Icon>  
        <TemplateID>bfeadf8e-a251-4109-b605-516b88e38c8d</TemplateID>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <DefaultName>Class.cs</DefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```  
  
 提供的信息 **\<TemplateData >** 元素保持不变。 **\<VSTemplateContainer >** 元素指向关联的模板的.vstemplate 文件  
  
 有关.vstman 文件的不同元素的详细信息，请参阅[Visual Studio 模板清单架构参考](../extensibility/visual-studio-template-manifest-schema-reference.md)。  
  
## <a name="upgrades-for-extensions-installed-with-an-msi"></a>与安装扩展的升级。MSI  
 某些基于 MSI 的扩展插件将模板部署到常用的模板位置，如下所示：  
  
- **\<Visual Studio 安装目录 > \Common7\IDE\\< ProjectTemplates/项模板 >**  
  
- **\<Visual Studio 安装目录 > \Common7\IDE\Extensions\\< ExtensionName\>\\< 项目/项模板 >**  
  
  如果你的扩展执行的基于 MSI 的部署，需要手动生成模板清单，并确保它包含在扩展安装程序中。 您应比较上面列出的.vstman 示例和[Visual Studio 模板清单架构参考](../extensibility/visual-studio-template-manifest-schema-reference.md)。 若要查看需要包含  
  
  应创建单独的项目和项模板清单，它们应指向根模板目录指定更高版本。 您应创建一个清单，每个扩展和区域设置。  
  
## <a name="troubleshooting-template-installation"></a>模板安装故障排除  
 如果遇到问题，部署项目或项模板，则可以启用诊断日志记录。  
  
1. 运行以下命令以设置注册表项来启用日志记录：  
  
    **reg 添加 HKCU\software\microsoft\visualstudio\15.0_Config\VSTemplate /v EnableTemplateDiscoveryLog /t REG_DWORD /d 1**  
  
2. 启动 Visual Studio，并启动新项目和新项对话框，以便初始化两个模板树。 模板日志现在显示在 **%LOCALAPPDATA%\Microsoft\VisualStudio\15.0\VsTemplateDiagnosticsList.csv**。 每个模板树初始化附加到此日志条目。  
  
   日志文件包含以下列：  
  
-   **FullPathToTemplate**，其中包含以下值：  
  
    -   1 表示基于清单的部署  
  
    -   0 为基于磁盘的部署的  
  
-   **TemplateFileName**  
  
-   其他模板属性

