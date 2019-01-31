---
title: “打开解决方案”命令 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.opensolution
helpviewer_keywords:
- Open Solution command
- File.OpenSolution command
ms.assetid: 61de76c8-69d7-4cdb-b605-e132f45d05d9
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 298609aa37557eebc52dce7ca6eada2f98f2096d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54759981"
---
# <a name="open-solution-command"></a>“打开解决方案”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
打开一个现有解决方案，关闭其他所有打开的解决方案。  
  
## <a name="syntax"></a>语法  
  
```  
File.OpenSolution filename  
```  
  
## <a name="arguments"></a>自变量  
 `Filename`  
 必需。 要打开的解决方案的完整路径和文件名。  
  
 `filename` 参数的语法要求用引号将包含空格的路径括起来。  
  
## <a name="remarks"></a>备注  
 键入内容时，自动完成功能会尝试查找正确的路径和文件名。  
  
## <a name="example"></a>示例  
 此示例打开解决方案 Test1.sln。  
  
```  
>File.OpenSolution "c:\MySolutions\Test1\Test1.sln"  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
