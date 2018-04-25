---
title: -SafeMode (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c8748a6dadaee41a5e615742715a92240b74ab8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
在安全模式下启动 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]，仅加载默认环境和服务。  
  
## <a name="syntax"></a>语法  
  
```  
devenv /SafeMode   
```  
  
## <a name="remarks"></a>备注  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 启动时，此开关可阻止所有第三方 VSPackages 加载，以此确保执行稳定。  
  
## <a name="description"></a>描述  
 以下示例在安全模式下启动 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。  
  
## <a name="code"></a>代码  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>请参阅  
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)