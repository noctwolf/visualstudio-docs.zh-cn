---
title: -Setup (devenv.exe) | Microsoft Docs
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
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
ms.assetid: 87608b7f-a156-400c-80f5-fc823f843e61
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f57de02f0d46a14574ef3f34d47f2f5e4018096b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49230606"
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
强制 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 合并所有可用的 Vspackage 中描述菜单、工具栏和命令组的资源元数据。  
  
## <a name="syntax"></a>语法  
  
```  
devenv /setup  
```  
  
## <a name="remarks"></a>备注  
 此开关不带参数。 `devenv /setup` 命令通常作为安装过程的最后一步给出。 使用 `/setup` 开关不会启动 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。  
  
 必须以管理员身份运行 `devenv` 才能使用 [/setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) 和 [/InstallVSTemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) 开关。  
  
## <a name="example"></a>示例  
 此示例展示包含 Vspackage 的 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 版本安装的最后一步。  
  
```  
devenv /setup  
```  
  
## <a name="see-also"></a>请参阅  
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)



