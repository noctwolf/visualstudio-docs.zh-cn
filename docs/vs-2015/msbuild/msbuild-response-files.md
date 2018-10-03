---
title: MSBuild 响应文件 | Microsoft Docs
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
- response files, MSBuild
- MSBuild, response files
- MSBuild, .rsp files
- .rsp files
ms.assetid: 9f53987b-20ee-470a-ab62-fce997bb5e15
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 71fdc29db3e2af66c85637648bb0703e7f7d80c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469823"
---
# <a name="msbuild-response-files"></a>MSBuild 响应文件
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[MSBuild 响应文件](https://docs.microsoft.com/visualstudio/msbuild/msbuild-response-files)。  
  
  
响应 (.rsp) 文件是包含 MSBuild.exe 命令行开关的文本文件。 每个开关可以单独占一行，或者所有开关仅占一行。 注释行以 # 符号开头。 @ 开关用于将另一个响应文件传递给 MSBuild.exe。  
  
 自动响应文件是在生成项目时 MSBuild.exe 自动使用的特殊 .rsp 文件。 MSBuild.rsp 文件必须位于 MSBuild.exe 所在的目录中，否则无法找到该文件。 可以编辑此文件，向 MSBuild.exe 指定默认命令行开关。 例如，如果每次生成项目时使用相同的记录器，则可将 /logger 开关添加到 MSBuild.rsp，每次生成项目后，MSBuild.exe 都会使用该记录器。  
  
## <a name="see-also"></a>请参阅  
 [MSBuild 参考](../msbuild/msbuild-reference.md)   
 [命令行参考](../msbuild/msbuild-command-line-reference.md)



