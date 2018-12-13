---
title: 如何：使用 MSBuild.exe 生成解决方案中的特定目标 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: af1322145ad262a15b5ad47560e7c79aceeccc2b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49245826"
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>如何：使用 MSBuild.exe 生成解决方案中的特定目标
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
你可以使用 MSBuild 在解决方案中生成特定项目的特定目标。  
  
### <a name="to-build-a-specific-target-of-a-specific-project-in-a-solution"></a>在解决方案中生成特定项目的特定目标  
  
1.  在命令行中，键入 `MSBuild.exe <SolutionName>.sln`，其中 `<SolutionName>` 对应于包含要执行的目标的解决方案的文件名。  
  
2.  指定 *ProjectName* 格式的 **/t** 开关后的目标：*TargetName*。  
  
## <a name="example"></a>示例  
 以下示例执行 `NotInSlnFolder` 项目的 `Rebuild` 目标，然后执行位于 `NewFolder` 解决方案文件夹的 `InSolutionFolder` 项目的 `Clean` 目标。  
  
```  
msbuild SlnFolders.sln /t:NotInSlnfolder:Rebuild;NewFolder\InSolutionFolder:Clean  
```  
  
## <a name="see-also"></a>请参阅  
 [命令行参考](../msbuild/msbuild-command-line-reference.md)   
 [MSBuild 参考](../msbuild/msbuild-reference.md)   
 [ MSBuild](msbuild.md)  
 [MSBuild 概念](../msbuild/msbuild-concepts.md)


