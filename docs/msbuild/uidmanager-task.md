---
title: UidManager 任务 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 59bcb413ab391f74f9d2713fe87b4384e30cc0c3
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49844557"
---
# <a name="uidmanager-task"></a>UidManager 任务
<xref:Microsoft.Build.Tasks.Windows.UidManager> 任务将检查、更新或删除唯一标识符 (UID)，以对源 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 文件中包含的所有 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] 元素进行本地化。  
  
## <a name="task-parameters"></a>任务参数  
  
| 参数 | 描述 |
|-------------------------| - |
| `IntermediateDirectory` | 可选 **String** 参数。<br /><br /> 指定用于备份由 **MarkupFiles** 参数指定的源 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 文件的目录。 |
| `MarkupFiles` | 必需的 **ITaskItem[]** 参数。<br /><br /> 指定要包含的源 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]文件，以用于 UID 检查、更新或删除。 |
| `Task` | 必需的 **String** 参数。<br /><br /> 指定想要执行的 UID 管理任务。 有效选项为“检查”、“更新”或“删除”。 |
  
## <a name="example"></a>示例  
 下例使用 <xref:Microsoft.Build.Tasks.Windows.UidManager> 任务来检查指定的源 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 文件是否包含具有适当 UID 的 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 元素。  
  
```xml  
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
 [WPF MSBuild 参考](../msbuild/wpf-msbuild-reference.md)   
 [任务参考](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild 参考](../msbuild/msbuild-reference.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)   
 [生成 WPF 应用程序 (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)   
 [如何：对应用程序进行本地化](/dotnet/framework/wpf/advanced/how-to-localize-an-application)