---
title: -SafeMode (devenv.exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 94e8e87f4440644f76906a70ea09a46282b109c2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "68163364"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

在安全模式下启动 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]，仅加载默认环境和服务。  
  
## <a name="syntax"></a>语法  
  
```  
devenv /SafeMode   
```  
  
## <a name="remarks"></a>备注  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 启动时，此开关可阻止所有第三方 VSPackages 加载，以此确保执行稳定。  
  
## <a name="description"></a>说明  
 以下示例在安全模式下启动 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。  
  
## <a name="code"></a>代码  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>另请参阅  
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)
