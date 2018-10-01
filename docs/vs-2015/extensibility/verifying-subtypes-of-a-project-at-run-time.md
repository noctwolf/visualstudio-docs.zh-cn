---
title: 在运行时验证项目的子类型 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- project subtypes
- check subtypes
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e77fa60687ecfebdae8555b516af678cf3966211
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471506"
---
# <a name="verifying-subtypes-of-a-project-at-run-time"></a>在运行时验证项目的子类型
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[验证在运行时项目子类型](https://docs.microsoft.com/visualstudio/extensibility/verifying-subtypes-of-a-project-at-run-time)。  
  
取决于自定义项目子类型的 VSPackage 应包括逻辑来查找子类型，以便它可以正常退出如果相应的子类型不存在。 以下过程说明如何验证存在指定的子类型。  
  
### <a name="to-verify-the-presence-of-a-subtype"></a>若要验证存在子类型  
  
1.  从为项目和解决方案对象中获取的项目层次结构<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>通过将以下代码添加到你的 VSPackage 的对象。  
  
    ```  
    EnvDTE.DTE dte;  
    dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
  
    EnvDTE.Project project;  
    project = dte.Solution.Projects.Item(1);  
  
    IVsSolution solution;  
    solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
  
    IVsHierarchy hierarchy;  
    hierarchy = solution.GetProjectOfUniqueName(project.UniqueName);  
  
    ```  
  
2.  强制转换为层次结构<xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected>接口。  
  
    ```  
    IVsAggregatableProjectCorrected AP;  
    AP = hierarchy as IVsAggregatableProjectCorrected;  
  
    ```  
  
3.  通过调用获取的项目类型 Guid 列表<xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected.GetAggregateProjectTypeGuids%2A>。  
  
    ```  
    string projTypeGuids = AP.GetAggregateProjectTypeGuids().ToUpper();  
  
    ```  
  
4.  检查指定的子类型的 GUID 的列表。  
  
    ```  
    // Replace the string "MyGUID" with the GUID of the subtype.  
    string guidMySubtype = "MyGUID";  
    if (projTypeGuids.IndexOf(guidMySubtype) > 0)  
    {  
        // The specified subtype is present.  
    }  
    ```  
  
## <a name="see-also"></a>请参阅  
 [项目子类型](../extensibility/internals/project-subtypes.md)   
 [项目子类型设计](../extensibility/internals/project-subtypes-design.md)   
 [项目子类型扩展的属性和方法](../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)

