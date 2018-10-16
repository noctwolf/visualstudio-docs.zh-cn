---
title: /DebugExe (devenv.exe) | Microsoft Docs
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
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 56ff98aa40e122b5067bd17d72334daf93164fe2
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49262647"
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
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



