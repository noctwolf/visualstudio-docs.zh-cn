---
title: UidManager 任务 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UidManager task [WPF MSBuild]
- UidManager task [WPF MSBuild], parameters
- managing UIDs when localizing XAML elements [WPF MSBuild]
- localizing XAML elements [WPF MSBuild], managing UIDs
- checking UIDs when localizing XAML elements [WPF MSBuild]
ms.assetid: 4fc7b5a5-11b0-46ca-9656-8c2a0b08d1fe
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8f64a91ddf1eea2bdd74bd64e2d33acfd4d60827
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472376"
---
# <a name="uidmanager-task"></a>UidManager 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[UidManager 任务](https://docs.microsoft.com/visualstudio/msbuild/uidmanager-task)。  
  
  
<xref:Microsoft.Build.Tasks.Windows.UidManager> 任务将检查、更新或删除唯一标识符 (UID)，以对源 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 文件中包含的所有 [!INCLUDE[TLA#tla_xaml](../includes/tlasharptla-xaml-md.md)] 元素进行本地化。  
  
## <a name="task-parameters"></a>任务参数  
  
|参数|描述|  
|---------------|-----------------|  
|`IntermediateDirectory`|可选 **String** 参数。<br /><br /> 指定用于备份由 **MarkupFiles** 参数指定的源 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 文件的目录。|  
|`MarkupFiles`|必需的 **ITaskItem[]** 参数。<br /><br /> 指定要包含的源 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)]文件，以用于 UID 检查、更新或删除。|  
|`Task`|必需的 **String** 参数。<br /><br /> 指定想要执行的 UID 管理任务。 有效选项为“检查”、“更新”或“删除”。|  
  
## <a name="example"></a>示例  
 下例使用 <xref:Microsoft.Build.Tasks.Windows.UidManager> 任务来检查指定的源 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 文件是否包含具有适当 UID 的 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 元素。  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.UidManager"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="UidManagerTask">  
    <UidManager  
      Task="Check"  
      MarkupFiles="Page1.xaml;Page2.xaml"  
      IntermediateDirectory="c:\UidManagerIntermediateDirectory" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>请参阅  
 [WPF MSBuild 引用](../msbuild/wpf-msbuild-reference.md)   
 [任务参考](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild 参考](../msbuild/msbuild-reference.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)   
 [Building a WPF Application (WPF)](http://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c) （生成 WPF 应用程序 (WPF)）  
 [如何：对应用程序进行本地化](http://msdn.microsoft.com/library/5001227e-9326-48a4-9dcd-ba1b89ee6653)



