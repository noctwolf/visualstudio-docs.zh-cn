---
title: 使用层关系图验证代码 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- layer diagrams, validating
- validation, layer diagrams
- validation, code
- code exploration, validating
- architecture, validating
- Visual Studio Ultimate, validating code
- validation, architecture
- validation, dependencies
- MSBuild, tasks
- MSBuild, layer diagrams
- MSBuild, validating code
ms.assetid: 70cbe55d-4b33-4355-b0a7-88c770a6f75c
caps.latest.revision: 84
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: 724ddcc00b1f49eb1f96e67d6b6e269933cb9d66
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49950480"
---
# <a name="validate-code-with-layer-diagrams"></a>用层关系图验证代码
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

要确保代码不与其设计冲突，可以在 Visual Studio 中使用层关系图验证代码。 这可帮助你：  
  
- 查找代码中的依赖项和层关系图上的依赖项之间的冲突。  
  
- 查找建议的更改可能会影响的依赖项。  
  
   例如，可以编辑层关系图来显示潜在的体系结构更改，然后对代码进行验证以查看受影响的依赖项。  
  
- 将代码重构或迁移到其他设计。  
  
   查找在将代码移动到其他体系结构时需要工作的代码或依赖项。  
  
  **要求**  
  
- Visual Studio  
  
- Team Foundation Build 服务器上的 Visual Studio，用于使用 Team Foundation Build 自动验证代码  
  
- 一个具有建模项目和层关系图的解决方案。 该层关系图必须链接到要验证的 Visual C# .NET 或 Visual Basic .NET 项目中的项。 请参阅[从代码创建层关系图](../modeling/create-layer-diagrams-from-your-code.md)。  
  
  若要查看支持此功能的 Visual Studio 的版本，请参阅 [体系结构和建模工具的版本支持](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)。  
  
  你可以从 Visual Studio 中打开的层关系图或从命令提示符手动验证代码。 你还可以在运行本地生成或 Team Foundation Build 时自动验证代码。 请参阅[第 9 频道视频： 设计和验证体系结构使用层关系图](http://go.microsoft.com/fwlink/?LinkID=252073)。  
  
> [!IMPORTANT]
>  如果想要使用 Team Foundation Build 运行层验证，则还必须在生成服务器上安装相同版本的 Visual Studio。  
  
-   [请参阅项是否支持验证](#SupportsValidation)  
  
-   [包括其他.NET 程序集和项目以进行验证](#IncludeReferences)  
  
-   [手动验证代码](#ValidateManually)  
  
-   [自动验证代码](#ValidateAuto)  
  
-   [层验证问题疑难解答](#TroubleshootingValidation)  
  
-   [了解和解决层验证错误](#UnderstandingValidationErrors)  
  
##  <a name="SupportsValidation"></a> 请参阅项是否支持验证  
 你可以将层链接到网站、Office 文档、纯文本文件和项目中跨多个应用共享的文件，但验证过程不包含这些内容。 如果引用的项目或程序集链接到单独的层，而且这些层之间没有依赖关系出现，则将不会出现验证错误。 除非代码使用此类引用，否则这些引用不被视为依赖项。  
  
1.  在层关系图中，选择一个或多个层，用鼠标右键单击你的选择，然后单击**查看链接**。  
  
2.  在中**层资源管理器**，看看**支持验证**列。 如果该值为 false，则项不支持验证。  
  
##  <a name="IncludeReferences"></a> 包括其他.NET 程序集和项目以进行验证  
 将项拖到层关系图中，对相应的.NET 程序集或项目的引用将自动添加到**层引用**建模项目中的文件夹。 此文件夹包含对验证过程中分析的程序集和项目的引用。 你也可以包含要验证的其他 .NET 程序集和项目，而无需将它们手动拖到层关系图上。  
  
1.  在中**解决方案资源管理器**，右键单击建模项目或**层引用**文件夹，，然后单击**添加引用**。  
  
2.  在中**添加引用**对话框中，选择程序集或项目，然后依次**确定**。  
  
##  <a name="ValidateManually"></a> 手动验证代码  
 如果你有一个打开的层关系图链接到解决方案项，则可以运行**验证**从关系图的快捷方式命令。 此外可以使用命令提示符处运行**msbuild**命令 **/p:ValidateArchitecture**自定义属性设置为**True**。 例如，在对代码进行更改时，请定期执行层验证以便能够提前捕获依赖项冲突。  
  
#### <a name="to-validate-code-from-an-open-layer-diagram"></a>从打开的层关系图中验证代码  
  
1.  右键单击关系图图面，然后依次**验证体系结构**。  
  
    > [!NOTE]
    >  默认情况下**生成操作**上的层关系图 (.layerdiagram) 文件的属性设置为**验证**，以便在验证过程中包括关系图。  
  
     **错误列表**窗口报告出现的任何错误。 有关验证错误的详细信息，请参阅[了解和纠正层验证错误](#UnderstandingValidationErrors)。  
  
2.  若要查看每个错误的源，请双击中的错误**错误列表**窗口。  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 可能会显示代码映射，而不是显示错误的根源。 若代码所依赖的程序集不是由层关系图指定的，或代码缺少层关系图所指定的依赖项，则会出现此情况。 评审代码图或代码，以确定此依赖关系是否应该存在。 有关代码图的详细信息，请参阅[映射解决方案之间的依赖项](../modeling/map-dependencies-across-your-solutions.md)。  
  
3.  若要管理错误，请参阅[管理验证错误](#ManageErrors)。  
  
#### <a name="to-validate-code-at-the-command-prompt"></a>在命令提示符处验证代码  
  
1. 打开 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 命令提示。  
  
2. 选择以下选项之一：  
  
   - 若要对照解决方案中的特定建模项目验证代码，请使用下面的自定义属性运行 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]。  
  
     ```  
     msbuild <FilePath+ModelProjectFileName>.modelproj /p:ValidateArchitecture=true  
     ```  
  
     - 或 -  
  
       浏览到包含建模项目文件 (.modelproj) 和层关系图的文件夹，然后使用下面的自定义属性运行 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]：  
  
     ```  
     msbuild /p:ValidateArchitecture=true   
     ```  
  
   - 若要对照解决方案中的所有建模项目验证代码，请使用下面的自定义属性运行 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]：  
  
     ```  
     msbuild <FilePath+SolutionName>.sln /p:ValidateArchitecture=true   
     ```  
  
     - 或 -  
  
       浏览到必须包含建模项目（包含层关系图）的解决方案文件夹，然后使用下面的自定义属性运行 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]：  
  
     ```  
     msbuild /p:ValidateArchitecture=true  
     ```  
  
     将列出发生的任何错误。 有关详细信息[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]，请参阅[MSBuild](../msbuild/msbuild.md)并[MSBuild 任务](../msbuild/msbuild-task.md)。  
  
   有关验证错误的详细信息，请参阅[了解和纠正层验证错误](#UnderstandingValidationErrors)。  
  
###  <a name="ManageErrors"></a> 管理验证错误  
 在开发过程中，你可能需要在验证期间禁止显示报告的某些冲突。 例如，你可能希望禁止显示你已解决或与特定情形不相关的错误。 禁止显示错误时，最好在 [!INCLUDE[esprfound](../includes/esprfound-md.md)] 中记录工作项。  
  
> [!WARNING]
>  必须已连接到 TFS 源代码管理 (SCC) 才可创建或链接到工作项。 如果尝试打开到其他 TFS SCC 的连接，则 Visual Studio 会自动关闭当前解决方案。 请先确保已连接到相应的 SCC，然后再尝试创建或链接到工作项。 在更高版本的 Visual Studio 中，如果未连接到 SCC，则菜单命令不可用。  
  
##### <a name="to-create-a-work-item-for-a-validation-error"></a>为验证错误创建工作项  
  
- 在中**错误列表**窗口中，右键单击错误，指向**创建工作项**，然后单击你想要创建的工作项的类型。  
  
  使用这些任务来管理中的验证错误**错误列表**窗口：  
  
|**若要**|**请执行以下步骤**|  
|------------|----------------------------|  
|禁止在验证过程中显示选定的错误|右键单击一个或多个所选的错误，指向**管理验证错误**，然后单击**禁止显示错误**。<br /><br /> 禁止显示的错误在显示时均带有删除线格式。 在你下次运行验证时，这些错误将不会显示。<br /><br /> 系统会在相应层关系图文件的 .suppressions 文件中对禁止显示的错误进行跟踪。|  
|停止禁止显示选定的错误|右键单击所选的禁止显示的错误，指向**管理验证错误**，然后单击**停止禁止显示错误**。<br /><br /> 在你下次运行验证时，这些所选的禁止显示的错误将会显示。|  
|还原中的所有禁止显示的错误**错误列表**窗口|中的任意位置右击**错误列表**窗口中，依次指向**管理验证错误**，然后单击**显示所有禁止显示的错误**。|  
|隐藏所有禁止显示的错误**错误列表**窗口|中的任意位置右击**错误列表**窗口中，依次指向**管理验证错误**，然后单击**隐藏所有禁止显示的错误**。|  
  
##  <a name="ValidateAuto"></a> 自动验证代码  
 每次运行本地生成时，都可以执行层验证。 如果你的团队使用 Team Foundation Build，则可使用能够通过创建自定义 MSBuild 任务指定的封闭签入来执行层验证，并使用生成报告来收集验证错误。 若要创建封闭的签入生成，请参阅[使用封闭的签入生成过程以验证更改](http://msdn.microsoft.com/library/9cfc8b9c-1023-40fd-8ab5-1b1bd9c172ec)。  
  
#### <a name="to-validate-code-automatically-during-a-local-build"></a>在本地生成期间自动验证代码  
  
-   使用文本编辑器打开建模项目 (.modelproj) 文件，然后包括以下属性：  
  
```  
<ValidateArchitecture>true</ValidateArchitecture>  
```  
  
 \- 或 -  
  
1. 在中**解决方案资源管理器**，右键单击包含层关系图或关系图的建模项目，然后单击**属性**。  
  
2. 在中**属性**窗口中，将建模项目**验证体系结构**属性设置为**True**。  
  
    这将在验证过程中包括建模项目。  
  
3. 在中**解决方案资源管理器**，单击你想要用于验证的层关系图 (.layerdiagram) 文件。  
  
4. 在中**属性**窗口中，请确保关系图的**生成操作**属性设置为**Validate**。  
  
    这将在验证过程中包括层关系图。  
  
   若要管理错误列表窗口中的错误，请参阅[管理验证错误](#ManageErrors)。  
  
#### <a name="to-validate-code-automatically-during-a-team-foundation-build"></a>在 Team Foundation Build 期间自动验证代码  
  
1. 在中**团队资源管理器**，双击生成定义，然后单击**进程**。  
  
2. 下**生成过程参数**，展开**编译**，并键入以下内容中的**MSBuild 参数**参数：  
  
    `/p:ValidateArchitecture=true`  
  
   有关验证错误的详细信息，请参阅[了解和纠正层验证错误](#UnderstandingValidationErrors)。 有关 [!INCLUDE[esprbuild](../includes/esprbuild-md.md)] 的详细信息，请参阅：  
  
-   [生成应用程序](http://msdn.microsoft.com/library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)  
  
-   [在生成过程中使用默认模板](http://msdn.microsoft.com/library/43930b12-c21b-4599-a980-2995e3d16e31)  
  
-   [修改基于 UpgradeTemplate.xaml 的旧式生成](http://msdn.microsoft.com/library/ee1a8259-1dd1-4a10-9563-66c5446ef41c)  
  
-   [自定义生成过程模板](http://msdn.microsoft.com/library/b94c58f2-ae6f-4245-bedb-82cd114f6039)  
  
-   [监视运行的生成的进度](http://msdn.microsoft.com/library/e51e3bad-2d1d-4b7b-bfcc-c43439c6c8ef)  
  
##  <a name="TroubleshootingValidation"></a> 层验证问题疑难解答  
 下表描述了层验证问题及其解决方法。 这些问题不同于代码与设计发生冲突而导致出现的错误。 有关这些错误的详细信息，请参阅[了解和纠正层验证错误](#UnderstandingValidationErrors)。  
  
|**问题**|**可能的原因**|**解决方法**|  
|---------------|------------------------|--------------------|  
|验证错误不按预期发生。|在解决方案资源管理器中，从同一建模项目中的其他层关系图复制的层关系图上，验证不起作用。 以这种方式复制的层关系图包含与原始层关系图相同的引用。|向建模项目中添加一个新的层关系图。<br /><br /> 将源层关系图中的元素复制到新关系图。|  
  
##  <a name="UnderstandingValidationErrors"></a> 了解和解决层验证错误  
 在对照层关系图验证代码时，如果代码与设计发生冲突，则会出现验证错误。 例如，以下情况可能导致发生验证错误：  
  
- 将项目指派给了错误的层。 在这种情况下，请移动项目。  
  
- 项目（例如类）以与你的体系结构相冲突的方式使用了其他类。 在这种情况下，请重构代码以移除依赖关系。  
  
  若要解决这些错误，请更新代码，直至验证过程中不出现其他错误为止。 可以反复执行此任务。  
  
  以下各节描述这些错误中使用的语法，解释了这些错误的含义，并提供了纠正或管理这些错误的方法。  
  
|**语法**|**说明**|  
|----------------|---------------------|  
|*ArtifactN*(*ArtifactTypeN*)|*ArtifactN*是与层在层关系图上关联的项目。<br /><br /> *ArtifactTypeN*是一种*ArtifactN*，如**类**或**方法**，例如：<br /><br /> MySolution.MyProject.MyClass.MyMethod(Method)|  
|*NamespaceNameN*|命名空间的名称。|  
|*LayerNameN*|层在层关系图上的名称。|  
|*DependencyType*|类型之间的依赖关系*Artifact1*并*Artifact2*。 例如， *Artifact1*已**调用**与关系*Artifact2*。|  
  
|**错误语法**|**错误说明**|  
|----------------------|---------------------------|  
|AV0001： 无效的依赖项： *Artifact1*(*ArtifactType1*)--> *Artifact2*(*ArtifactType2*)<br /><br /> 层： *LayerName1*， *LayerName2* &#124;的依赖关系： *DependencyType*|*Artifact1*中*LayerName1*不应依赖于*Artifact2*中*LayerName2*因为*LayerName1*没有直接的依赖关系*LayerName2*。|  
|AV1001： 无效 Namespace:*项目*<br /><br /> 层： *LayerName* &#124;所需 Namespace: *NamespaceName1* &#124;当前 Namespace: *NamespaceName2*|*LayerName*要求其关联的项目必须属于*NamespaceName1*。 *项目*处于*NamespaceName2*，而非*NamespaceName1*。|  
|AV1002： 依赖于禁止 Namespace: *Artifact1*(*ArtifactType1*) &#124; *Artifact2*(*ArtifactType2*)<br /><br /> 层： *LayerName* &#124;禁止 Namespace:*命名空间名称*&#124;的依赖关系： *DependencyType*|*LayerName*要求其关联的项目必须不依赖于*命名空间名称*。 *Artifact1*不能依赖于*Artifact2*因为*Artifact2*处于*命名空间名称*。|  
|AV1003： 在禁止 Namespace:*项目*(*ArtifactType*)<br /><br /> 层： *LayerName* &#124;禁止 Namespace:*命名空间名称*|*LayerName*要求其关联的项目不能属于*命名空间名称*。 *项目*属于*命名空间名称*。|  
|AV3001： 缺少链接： 层 '*LayerName*链接到*项目*找不到其中。 是否缺少程序集引用?|*LayerName*链接到找不到的项目。 例如，由于建模项目缺少对包含某个类的程序集的引用，因此可能缺少指向该类的链接。|  
|AV9001: 体系结构分析遇到了内部错误。 结果可能不完整。 有关详细信息，请参阅详细的生成事件日志或输出窗口。|有关更多详细信息，请参阅生成事件日志或输出窗口。|  
  
## <a name="security"></a>安全性  
  
## <a name="see-also"></a>请参阅  
 [在开发过程中验证系统](../modeling/validate-your-system-during-development.md)



