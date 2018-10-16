---
title: -Log (devenv.exe) | Microsoft Docs
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
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6e3c8ee5d8c0bc5d68159fe0b40f22dda74f564f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49292027"
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
将所有活动记录到日志文件以用于疑难解答。 此文件在你至少调用一次 `devenv /log` 后显示。 默认情况下，日志文件为：  
  
 %APPDATA%\Microsoft\VisualStudio\\Version\ActivityLog.xml  
  
 其中，“版本”是 Visual Studio 的版本。 但是，可以指定一个不同的路径和文件名。  
  
## <a name="syntax"></a>语法  
  
```  
Devenv /log Path\NameOfLogFile  
```  
  
## <a name="remarks"></a>备注  
 此开关必须显示在命令行的结尾，位于所有其他开关之后。  
  
 对于你使用 /log 开关调用的所有 Visual Studio 实例，都会记录日志。 对于不使用此开关调用的 Visual Studio 实例，将不记录日志。  
  
## <a name="see-also"></a>请参阅  
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)



