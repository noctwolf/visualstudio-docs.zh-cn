---
title: /DebugExe (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0882ae58919cafae71bcb056e74533b7ce64a4e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)
打开要调试的指定可执行文件。  
  
## <a name="syntax"></a>语法  
  
```  
Devenv /debugexe ExecutableFile  
```  
  
## <a name="arguments"></a>自变量  
 `ExecutableFile`  
 必须的。 .exe 文件的路径和文件名称。  
  
 如果找不到 .exe 文件或不存在，不会显示任何警告或错误，并且 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 启动正常。  
  
## <a name="remarks"></a>备注  
 `ExecutableFile` 形式参数后的任何字符串都作为实际参数传递到此文件。  
  
## <a name="example"></a>示例  
 以下示例打开文件 `MyApplication.exe` 进行调试。  
  
```  
Devenv.exe /debugexe MyApplication.exe  
```  
  
## <a name="see-also"></a>请参阅  
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)