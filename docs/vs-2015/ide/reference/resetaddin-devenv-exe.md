---
title: -ResetAddin (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disable addin
- addin state
- reset addin
ms.assetid: 9e339c8d-d768-4d86-8f45-2f479fc8255b
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: df5fe62efd783551a483853543ddb30312e64c65
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49213663"
---
# <a name="resetaddin-devenvexe"></a>/ResetAddin (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
移除与指定外接程序关联的命令和命令用户界面。  
  
## <a name="syntax"></a>语法  
  
```  
Devenv /ResetAddin AddIn  
```  
  
## <a name="arguments"></a>自变量  
 `AddIn`  
 可选。 外接程序的命令名称。  
  
## <a name="remarks"></a>备注  
 默认情况下，外接程序的命令名称等于 *\<AddInSolutionName>*.Connect *.\<AddInSolutionName>*，并在 Connect.cs 中显示为 `Exec` 方法的 `commandName` 参数。 还可以通过开始在 Visual Studio 的“命令”窗口中键入外接程序的名称并使用 Intellisense 填充其余部分来验证命令名称。  
  
## <a name="example"></a>示例  
 以下示例启动 Visual Studio 并阻止 `MyAddin` 外接程序在启动时运行。  
  
```  
Devenv.exe /ResetAddin MyAddin.Connect.MyAddin  
```  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)



