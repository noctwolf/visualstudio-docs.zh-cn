---
title: "WriteLinesToFile 任务 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#WriteLinesToFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- WriteLinesToFile task [MSBuild]
- MSBuild, WriteLinesToFile task
ms.assetid: 9c8862ac-8da5-4437-9430-ecc30421f1c9
caps.latest.revision: "9"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1c284fefa1ed296e08049bd5bb7ea5df757107ce
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="writelinestofile-task"></a>WriteLinesToFile 任务
将指定项的路径写入指定的文本文件。  
  
## <a name="task-parameters"></a>任务参数  
 下表描述了 `WriteLinestoFile` 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`File`|必选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定要将项写入到的文件。|  
|`Lines`|可选 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 参数。<br /><br /> 指定要写入到文件的项。|  
|`Overwrite`|可选 `Boolean` 参数。<br /><br /> 如果为 `true`，该任务覆盖文件中的任何现有内容。|  
|`Encoding`|可选 `String` 参数。<br /><br /> 选择字符编码，例如“Unicode”。  另请参阅<xref:System.Text.Encoding>。|  
  
## <a name="remarks"></a>备注  
 如果 `Overwrite` 为 `true`，创建一个新文件，向其中写入内容，然后关闭文件。 如果目标文件已存在，则覆盖该文件。 如果 `Overwrite` 为 `false`会将内容追加到文件中，如果目标文件还不存在则创建该文件。  
  
 除上面列出的参数外，此任务还从 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数，后者自身继承自 <xref:Microsoft.Build.Utilities.Task> 类。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="example"></a>示例  
 以下示例使用 `WriteLinesToFile` 任务，将 `MyItems` 项集合中项的路径写入到 `MyTextFile` 项集合指定的文件中。  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyTextFile Include="Items.txt"/>  
        <MyItems Include="*.cs"/>  
    </ItemGroup>  
  
    <Target Name="WriteToFile">  
        <WriteLinesToFile  
            File="@(MyTextFile)"  
            Lines="@(MyItems)"  
            Overwrite="true"  
            Encoding="Unicode"/>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)