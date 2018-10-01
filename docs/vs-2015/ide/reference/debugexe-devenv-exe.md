---
title: /DebugExe (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f58db37f353cddd7444e7ea185dc07c0ec6cd603
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469057"
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[/debugexe (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/debugexe-devenv-exe)。  
  
  
打开要调试的指定可执行文件。  
  
## <a name="syntax"></a>语法  
  
```  
Devenv /debugexe ExecutableFile  
```  
  
## <a name="arguments"></a>自变量  
 `ExecutableFile`  
 必须的。 .exe 文件的路径和文件名称。  
  
 如果找不到 .exe 文件或不存在，不会显示任何警告或错误，并且 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 启动正常。  
  
## <a name="remarks"></a>备注  
 `ExecutableFile` 形式参数后的任何字符串都作为实际参数传递到此文件。  
  
## <a name="example"></a>示例  
 以下示例打开文件 `MyApplication.exe` 进行调试。  
  
```  
Devenv.exe /debugexe MyApplication.exe  
```  
  
## <a name="see-also"></a>请参阅  
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)



