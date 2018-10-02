---
title: Visual Studio 模板清单架构参考 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc7d0a81-0df5-41a9-a912-1b30e5da1d13
caps.latest.revision: 4
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b079e6b7356cdd84a98314beef95f4b1a8fbc5ee
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471211"
---
# <a name="visual-studio-template-manifest-schema-reference"></a>Visual Studio 模板清单架构参考
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[Visual Studio 模板清单架构参考](https://docs.microsoft.com/visualstudio/extensibility/visual-studio-template-manifest-schema-reference)。  
  
此架构描述了为 Visual Studio 项目或项模板，生成的 Visual Studio 模板清单 (.vstman) 文件格式，并描述位置和有关模板的其他相关信息。  
  
 ： 由于没有单独的项目和项目模板目录，清单应该永远不会同时有的项和项目模板。  
  
> [!IMPORTANT]
>  此清单是从 Visual Studio"15"预览版 2 开始，提供。  
  
## <a name="vstemplatemanifest-element"></a>VSTemplateManifest 元素  
 清单的根元素。  
  
### <a name="attributes"></a>特性  
  
-   **版本**： 一个字符串，表示模板清单的版本。 必须的。  
  
-   **区域设置**： 一个表示区域设置或区域设置的模板清单的字符串。 区域设置值应用于所有模板，因此你必须将每个区域使用单独的清单。 可选。  
  
### <a name="child-elements"></a>子元素  
  
-   **VSTemplateContainer**可选。  
  
-   **VSTemplateDir**可选。  
  
### <a name="parent-element"></a>父元素  
 无。  
  
## <a name="vstemplatecontainer"></a>VSTemplateContainer  
 模板容器的清单元素。 清单都有针对它定义了每个模板的一个模板容器。  
  
### <a name="attributes"></a>特性  
 **VSTemplateType** ： 一个字符串值，指定模板类型 (`"Project"`， `"Item"`，或`"ProjectGroup"`)。 必需  
  
### <a name="child-elements"></a>子元素  
  
-   **RelativePathOnDisk**： 磁盘上的模板文件的相对路径。 此位置还定义模板的放置在模板树中所示**新的项目**或**新项**对话框。 有关模板部署为一个目录和单个文件，此路径是指包含模板文件的目录。 有关模板部署为一个.zip 文件，此路径应为.zip 文件的路径。  
  
-   **VSTemplateHeader** ： 一个[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)描述该标头的元素。  
  
### <a name="parent-element"></a>父元素  
 **VSTemplateManifest**  
  
## <a name="vstemplatedir"></a>VSTemplateDir  
 介绍模板所在的目录。 清单可以包含多个**VSTemplateDir**条目提供本地化的名称和排序顺序的目录，以控制它们在模板类别树中的外观。  
  
 由于其设计**VSTemplateDir**条目应仅在非区域设置指定的清单中出现。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
-   **RelativePath**： 模板的路径。 可能每个路径，只有一个条目，因此第一个获胜的所有清单。  
  
-   **LocalizedName**： 一个**NameDescriptionIcon**元素，它指定本地化的名称。 可选。  
  
-   **SortOrder** ： 一个字符串，指定排序顺序。 可选。  
  
-   **ParentFolderOverrideName**： 重写的父文件夹的名称。 可选。 此元素具有**名称**特性，它是一个字符串值，指定的名称。  
  
### <a name="parent-element"></a>父元素  
 **VSTemplateManifest**  
  
## <a name="namedescriptionicon"></a>NameDescriptionIcon  
 指定的名称和描述，可能是已本地化的模板。 请参阅**LocalizedName**上面。  
  
### <a name="attributes"></a>特性  
  
-   **包**： 一个字符串值，指定的包。 可选。  
  
-   **ID**： 一个字符串值，指定该 id。 可选。  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-element"></a>父元素  
 **LocalizedName**  
  
## <a name="examples"></a>示例  
 下面是项目模板.vstman 文件的示例。  
  
```xml  
<VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Project">  
    <RelativePathOnDisk>CSharp\1033\TestProjectTemplate</RelativePathOnDisk>  
    <TemplateFileName>TestProjectTemplate.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>TestProjectTemplate</Name>  
        <Description>TestProjectTemplate</Description>  
        <Icon>TestProjectTemplate.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <SortOrder>1000</SortOrder>  
        <TemplateID>aac0aeea-7883-4003-992f-937d53d70ab1</TemplateID>  
        <CreateNewFolder>true</CreateNewFolder>  
        <DefaultName>TestProjectTemplate</DefaultName>  
        <ProvideDefaultName>true</ProvideDefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```  
  
 下面是项模板.vstman 文件的示例。  
  
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

