---
title: -SafeMode (devenv.exe) | Microsoft Docs
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
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b785a3e43726522f6e6cc6ce99dec4bf3815c81d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49230069"
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
  
## <a name="description"></a>描述  
 以下示例在安全模式下启动 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。  
  
## <a name="code"></a>代码  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>请参阅  
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)



