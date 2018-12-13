---
title: “添加现有项目”命令 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- file.addexistingproject
helpviewer_keywords:
- Add Existing Project command
- File.AddExistingProject
ms.assetid: 71cf3e31-c76b-405b-ad6a-1b1bc654bd40
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c881f32594ee6327dfba9792fa83bd2d092efcf9
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49267639"
---
# <a name="add-existing-project-command"></a>“添加现有项目”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
将现有项目添加到当前解决方案中。  
  
## <a name="syntax"></a>语法  
  
```  
File.AddExistingProject filename  
```  
  
## <a name="arguments"></a>自变量  
 `filename`  
 可选。 待添加到解决方案的项目的完整路径、项目名称和扩展名。  
  
 如果 `filename` 参数包含空格，则必须将其放在引号内。  
  
 如果未指定文件名，该命令将打开文件对话框，以便用户可以选取一个项目。  
  
## <a name="remarks"></a>备注  
 键入内容时，自动完成功能会尝试查找正确的路径和文件名。  
  
## <a name="example"></a>示例  
 此示例向当前解决方案中添加 [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] 项目 - TestProject1。  
  
```  
>File.AddExistingProject "c:\visual studio projects\TestProject1.vbproj"  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



