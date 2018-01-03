---
title: -SafeMode (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 17a8d92075f558e1e00bbba04f2c3ae955056b61
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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