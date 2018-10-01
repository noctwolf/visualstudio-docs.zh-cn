---
title: -ResetSettings (devenv.exe) | Microsoft Docs
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
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 25697a792b0c48746a1d7840b8091ea718f5cdc7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472425"
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[-ResetSettings (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/resetsettings-devenv-exe)。  
  
  
还原 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 默认设置并自动启动 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE。 可选择将这些设置重置为指定的 .vssettings 文件。  
  
 默认设置由首次启动 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 时选择的配置文件决定。  
  
## <a name="syntax"></a>语法  
  
```  
Devenv /ResetSettings SettingsFile  
```  
  
## <a name="arguments"></a>自变量  
 `SettingsFile`  
 .vssettings 文件的完整路径和名称应用于 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。  
  
 若要还原常规开发设置配置文件，请使用 `General`。  
  
## <a name="remarks"></a>备注  
 如果未指定任何 `SettingsFile`，在下次启动 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 时，系统将提示选择默认的设置集合。  
  
## <a name="example"></a>示例  
 下面的命令行应用 `MySettings.vssettings` 文件中存储的设置。  
  
```  
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"  
```  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)



