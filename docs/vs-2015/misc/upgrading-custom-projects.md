---
title: 升级自定义项目 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading project systems
- projects [Visual Studio SDK], upgrading
- project system upgrades [Visual Studio]
ms.assetid: 262ada44-7689-44d8-bacb-9c6d33834d4e
caps.latest.revision: 11
manager: douge
ms.openlocfilehash: 5c3fd31cfc7cfbf3f7dd687d38483f5bb62703ca
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479344"
---
# <a name="upgrading-custom-projects"></a>升级自定义项目
如果你更改保留在产品的不同 Visual Studio 版本之间的项目文件中的信息，则你需要支持将项目文件从旧版本升级到新版本。 若要支持升级，您可以参与**Visual Studio 转换向导**，实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>接口。 此接口包含可用于复制升级的唯一机制。 项目的升级作为解决方案打开的一部分而发生。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>接口由项目工厂实现或至少应该可以从项目工厂。  
  
 使用的旧机制<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>接口仍受支持，但从概念上讲升级项目系统打开项目的一部分。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>因此调用接口[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]环境，即使<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>调用或实现接口。 这种方法，可使用<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>来实现复制和项目仅部分升级，并通过委托的工作位置 （可能在新位置中） 来完成其余<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>接口。  
  
 有关示例实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>，请参阅[VSSDK 示例](../misc/vssdk-samples.md)。  
  
 项目升级时出现下列情况：  
  
-   如果文件是项目不能支持的较新格式，则它必须返回一个指出此情况的错误。 这假定你产品的较旧版本（例如，Visual Studio .NET 2003）包含检查版本的代码。  
  
-   如果<xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS>中指定标志<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A>方法，则升级将实现为就地升级之前打开项目。  
  
-   如果<xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS>中指定标志<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A>作为复制升级实现方法，在升级。  
  
-   如果<xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS>中指定标志<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A>调用，则已提示用户由环境之后打开该项目作为就地升级，升级项目文件。 例如，当用户打开解决方案的较旧版本时，环境会提示用户升级。  
  
-   如果<xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS>中未指定标志<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A>调用，则必须提示用户升级项目文件。  
  
     下面是一个升级提示消息示例：  
  
     “项目“%1”由 Visual Studio 的较旧版本创建。 如果使用此版本的 Visual Studio 打开它，你将不能用较旧版本的 Visual Studio 打开它。 是否要继续并打开此项目？”  
  
### <a name="to-implement-ivsprojectupgradeviafactory"></a>实现 IVsProjectUpgradeViaFactory  
  
1.  实现的方法<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>接口，特别是<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A>方法在项目工厂实现中，或使该实现可从项目工厂实现调用。  
  
2.  如果你想要执行就地升级作为解决方案打开的一部分，提供该标志<xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS>作为`VSPUVF_FLAGS`中的参数在<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A>实现。  
  
3.  如果你想要执行就地升级作为解决方案打开的一部分，提供该标志<xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS>作为`VSPUVF_FLAGS`中的参数在<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A>实现。  
  
4.  有关这两个步骤 2 和 3，实际文件升级步骤，使用<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>，如中所述，可以实现"实现`IVsProjectUpgade`"部分，或您可以将实际文件升级委派到<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>。  
  
5.  使用的方法<xref:Microsoft.VisualStudio.Shell.Interop.IVsUpgradeLogger>发布升级相关的用户使用 Visual Studio 迁移向导的消息。  
  
6.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileUpgrade> 接口用于实现任何类型的文件升级，都需要作为项目升级的一部分执行。 此接口不从调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>，但会将其作为一种机制，若要升级的项目系统，但主项目系统的一部分的文件可能不是直接感知到。 例如，如果编译器相关文件和属性未由处理项目系统其余部分的同一开发团队处理，则可能会发生这种情况。  
  
## <a name="ivsprojectupgrade-implementation"></a>IVsProjectUpgrade 实现  
 如果项目系统实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>仅，它不能参与**Visual Studio 转换向导**。 但是，即使你实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>接口，您可以仍将文件升级委派到<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>实现。  
  
#### <a name="to-implement-ivsprojectupgrade"></a>实现 IVsProjectUpgrade  
  
1.  当用户尝试打开一个项目，<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A>打开该项目并在其他任何用户之前采取措施的项目后，由环境调用的方法。 如果用户已提示升级解决方案，则<xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS>标志将传入`grfUpgradeFlags`参数。 如果用户打开的项目直接，此类通过使用**添加现有项目**命令，则<xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS>标志不会传递并需要提示用户升级项目。  
  
2.  在响应<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A>调用时，该项目必须评估是否升级项目文件。 如果项目不需要将项目类型升级到新版本，则可以只返回<xref:Microsoft.VisualStudio.VSConstants.S_OK>标志。  
  
3.  如果项目需要将项目类型升级到新版本，则它必须确定是否可以通过调用修改项目文件<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>方法并传入的值<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags>为`rgfQueryEdit`参数。 该项目接下来需要执行以下操作：  
  
    -   如果`VSQueryEditResult`中返回值`pfEditCanceled`参数是<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult>，则可以继续升级，因为项目文件可以进行编写。  
  
    -   如果`VSQueryEditResult`中返回值`pfEditCanceled`参数是<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult>并`VSQueryEditResult`的值具有<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags>位集，然后<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A>必须返回失败，因为用户应该解决权限问题本身。 该项目接下来应执行以下操作：  
  
         将错误报告给用户，通过调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A>。 并返回<xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes>错误代码以便<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>。  
  
    -   如果`VSQueryEditResult`值是<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult>并`VSQueryEditResultFlags`的值具有<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags>位集，则应通过调用签出项目文件<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>(<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags>， <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags>，...)。  
  
4.  如果<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>项目文件上的调用会导致要签出的文件和要检索的最新版本，然后卸载并重新加载项目。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A>创建的项目的另一个实例后再次调用方法。 在这第二次调用上，项目文件可以写入磁盘；建议项目使用 .OLD 扩展名按以前的格式保存项目文件的副本、进行必要的升级更改，并以新格式保存项目文件。 同样，如果升级过程的任何部分失败，该方法必须指示失败通过返回<xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes>。 这将导致项目无法在解决方案资源管理器中卸载。  
  
     务必要了解有关这种情况在其环境中发生的完整过程的调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>（指定 ReportOnly 的值） 的方法返回<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult>和<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags>标志。  
  
5.  用户尝试打开项目文件。  
  
6.  环境调用你<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A>实现。  
  
7.  如果<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A>将返回`true`，然后环境调用你<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A>实现。  
  
8.  环境调用你<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.Load%2A>实现，以打开文件，例如，初始化项目对象 Project1。  
  
9. 环境调用你的 `IVsProjectUpgrade::UpgradeProject` 实现来确定是否需要升级项目文件。  
  
10. 在调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>中的一个值，然后传入<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags>为`rgfQueryEdit`参数。  
  
11. 该环境将返回<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult>有关`VSQueryEditResult`并<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags>中设置位`VSQueryEditResultFlags`。  
  
12. 你<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>实现调用`IVsQueryEditQuerySave::QueryEditFiles`(<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags>， <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags>)。  
  
 此调用可能导致项目文件的新副本被签出、最新版本被检索，以及需要重新加载项目文件。 在这种情况下，将发生以下两种情况中的一种：  
  
-   如果处理您自己的项目重载，则环境将调用你<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A>(VSITEMID_ROOT) 实现。 当你收到此调用时，请重新加载项目的第一个实例 (Project1) 并继续升级项目文件。 如果返回处理您自己的项目重载则环境知道`true`有关<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>(<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>)。  
  
-   如果不处理自己的项目重载，则返回`false`有关<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>(<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>)。 在这种情况下前, <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>([QEF_ForceEdit_NoPrompting](assetId:///T:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags?qualifyHint=False&autoUpgrade=True)， [QEF_DisallowInMemoryEdits](assetId:///T:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags?qualifyHint=False&autoUpgrade=True)，) 返回时，环境将创建另一个新项目，如 Project2，实例作为如下所示：  
  
    1.  环境调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.Close%2A>上在第一个项目对象 Project1，因此使此对象处于非活动状态。  
  
    2.  环境调用你的 `IVsProjectFactory::CreateProject` 实现来创建项目的第二个实例 Project2。  
  
    3.  环境调用你的 `IPersistFileFormat::Load` 实现，以打开该文件并初始化第二个项目对象 Project2。  
  
    4.  环境第二次调用 `IVsProjectUpgrade::UpgradeProject` 以确定是否应升级项目对象。 但是，此调用在项目的第二个新实例 Project2 上进行。 这就是在解决方案中打开的项目。  
  
        > [!NOTE]
        >  第一个项目，Project1，放置处于非活动状态，则必须返回的实例中<xref:Microsoft.VisualStudio.VSConstants.S_OK>首次调用你<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A>实现。 请参阅[基本项目](http://msdn.microsoft.com/en-us/385fd2a3-d9f1-4808-87c2-a3f05a91fc36)的实现`IVsProjectUpgrade::UpgradeProject`。  
  
    5.  在调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>中的一个值，然后传入<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags>为`rgfQueryEdit`参数。  
  
    6.  该环境将返回<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult>和升级可以继续，因为项目文件可以进行编写。  
  
 如果您不能升级，则返回<xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes>从`IVsProjectUpgrade::UpgradeProject`。 如果不需要升级或你选择不升级，请将 `IVsProjectUpgrade::UpgradeProject` 调用视作不执行任何操作。 如果返回<xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes>，占位符节点添加到你的项目的解决方案。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 转换向导](http://msdn.microsoft.com/en-us/4acfd30e-c192-4184-a86f-2da5e4c3d83c)   
 [升级项目项](../misc/upgrading-project-items.md)   
 [项目](../extensibility/internals/projects.md)