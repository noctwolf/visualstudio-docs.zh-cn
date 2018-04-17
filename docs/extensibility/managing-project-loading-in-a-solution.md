---
title: 管理解决方案中的项目加载 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- solutions, managing project loading
ms.assetid: 097c89d0-f76a-4aaf-ada9-9a778bd179a0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d0e479a96252710d1f7e6285ffaaa2baf383c061
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="managing-project-loading-in-a-solution"></a>在解决方案中的管理项目加载
Visual Studio 解决方案可以包含大量的项目。 默认 Visual Studio 行为是在打开解决方案时，时间加载解决方案中的所有项目，而不是允许用户访问任何项目，直到所有它们完成加载。 当项目加载过程将持续超过 2 分钟时，将显示进度栏，显示加载的项目数量以及项目总数。 用户可以在具有多个项目的解决方案中使用时，卸载项目，但此过程也有些缺点： 已卸载的项目不属于重新生成解决方案命令中，生成和关闭 IntelliSense 类型的描述和的成员项目不会显示。  
  
 开发人员可以减少解决方案加载时间和管理项目通过创建解决方案负载管理器中加载行为。 解决方案负载管理器可以确保在开始后台生成之前加载了项目、 延迟后台加载其他后台任务都完成时，直到和执行其他项目负载管理任务。  
  
## <a name="creating-a-solution-load-manager"></a>创建解决方案负载管理器  
 开发人员可以创建解决方案负载 manager 通过实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager>并告知 Visual Studio 解决方案负载管理器处于活动状态。  
  
#### <a name="activating-a-solution-load-manager"></a>激活解决方案负载管理器  
 Visual Studio 允许只有一个解决方案负载管理器在给定时间，因此当你想要激活解决方案负载时，你必须告知 Visual Studio 管理器。 如果第二个解决方案负载管理器激活更高版本上，解决方案负载管理器将断开连接。  
  
 你必须获取<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>服务并将设置<xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>属性：  
  
```csharp  
IVsSolution pSolution = GetService(typeof(SVsSolution)) as IVsSolution;  
object objLoadMgr = this;   //the class that implements IVsSolutionManager  
pSolution.SetProperty((int)__VSPROPID4.VSPROPID_ActiveSolutionLoadManager, objLoadMgr);  
```  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager.OnDisconnect%2A>正在关闭 Visual Studio 或其他包已活动解决方案负载管理器作为更改通过调用时调用方法<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.SetProperty%2A>与<xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>属性。  
  
#### <a name="strategies-for-different-kinds-of-solution-load-manager"></a>为不同类型的解决方案的策略加载管理器  
 你可以以不同的方式，具体取决于它们为了管理的解决方案的类型来实现解决方案负载管理器。  
  
 如果解决方案负载管理器旨在管理一般情况下加载的解决方案，它可实现 VSPackage 的一部分。 通过添加情况下，包应设置为自动上载<xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute>值为 VSPackage 上<xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionOpening_guid>。 然后可以在中激活解决方案负载管理器<xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A>方法。  
  
> [!NOTE]
>  有关自动加载的包的详细信息，请参阅[加载 Vspackage](../extensibility/loading-vspackages.md)。  
  
 因为 Visual Studio 能够识别仅的最后一个解决方案负载管理器将激活，常规解决方案负载管理器应该始终首先检测是否存在现有的负载管理器在激活本身之前。 如果解决方案服务上调用 GetProperty()<xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>返回`null`，没有任何活动解决方案负载管理器。 如果它不返回 null，请检查对象是否与你的解决方案负载管理器相同。  
  
 如果解决方案负载管理器旨在管理只有几种解决方案，VSPackage 可以解决方案加载事件订阅 (通过调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A>)，并使用事件处理程序<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A>激活解决方案负载管理器。  
  
 如果解决方案负载管理器旨在管理仅特定解决方案，可以通过调用保留解决方案文件的一部分的激活信息<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A>预解决方案部分。  
  
 特定解决方案负载经理应停用本身中<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents.OnAfterCloseSolution%2A>事件处理程序，为了不与其他解决方案负载管理器发生冲突。  
  
 如果你需要解决方案负载管理器，若要保存全局项目负载属性 （例如，在选项页上设置的属性），则可以激活中的解决方案负载管理器仅<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>事件处理程序中，保留在解决方案属性中，设置然后停用解决方案负载管理器。  
  
## <a name="handling-solution-load-events"></a>处理解决方案加载事件  
 若要订阅解决方案加载事件，调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A>激活解决方案负载管理器。 如果你实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents>，你可以对与不同的项目加载属性相关的事件作出响应。  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A>： 此事件之前打开解决方案时激发。
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeBackgroundSolutionLoadBegins%2A>： 此事件激发后的解决方案是完全加载，但在后台之前加载的项目将重新开始计算。
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterBackgroundSolutionLoadComplete%2A>： 此事件激发后最初完全加载解决方案，无论存在解决方案负载管理器。 后台负载或需加载时该解决方案将成为完全加载后，它也会激发。 同时，<xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExistsAndFullyLoaded_guid>重新激活。  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnQueryBackgroundLoadProjectBatch%2A>： 此事件在加载的一个项目 （或项目） 之前激发。 若要确保加载项目之前完成其他后台进程，设置`pfShouldDelayLoadToNextIdle`到**true**。  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeLoadProjectBatch%2A>： 此事件激发时一批的项目将被加载。 如果`fIsBackgroundIdleBatch`为 true，项目要加载在后台中; 如果`fIsBackgroundIdleBatch`为 false，项目是要加载以同步方式由于用户请求，例如用户如果展开解决方案资源管理器中的挂起项目。 你可以处理此事件来完成否则将需要在中，进行的昂贵工作<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>。  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterLoadProjectBatch%2A>： 此事件在加载项目一批之后激发。  
  
## <a name="detecting-and-managing-solution-and-project-loading"></a>检测和管理解决方案和项目加载  
 若要检测的项目和解决方案的加载状态，调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProperty%2A>使用以下值：  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>:`var`返回`true`解决方案和所有项目将加载，否则如果`false`。  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>:`var`返回`true`如果项目一批当前正在加载的是在后台，否则`false`。  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>:`var`返回`true`如果项目一批当前正在加载的是以同步方式因用户命令或其他显式负载，而否则`false`。  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID2>:`var`返回`true`解决方案当前正在关闭，否则如果`false`。  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>:`var`返回`true`如果目前打开解决方案，否则`false`。  
  
 你还可以确保通过调用以下方法之一加载项目和解决方案：  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureSolutionIsLoaded%2A>： 调用此方法强制加载完毕，该方法返回的解决方案中的项目。  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectIsLoaded%2A>： 调用此方法强制中的项目`guidProject`加载完毕，该方法返回。  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectsAreLoaded%2A>： 调用此方法强制中的项目`guidProjectID`加载完毕，该方法返回。  
