---
title: -Updateconfiguration (devenv.exe) | Microsoft Docs
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
- /updateconfiguration Devenv switch
- Devenv, /updateconfiguration switch
- updateconfiguration Devenv switch
ms.assetid: 9a1084cc-8b68-4ccc-aaea-f95939164338
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 31fd7f52ad2be89a3e6a40a76948aea0d8cc8bfc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476810"
---
# <a name="updateconfiguration-devenvexe"></a>/Updateconfiguration (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[-Updateconfiguration (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/updateconfiguration-devenv-exe)。  
  
  
通知 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 合并系统上的 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 包，并检查 MEF 缓存中是否有任何更改。  
  
## <a name="syntax"></a>语法  
  
```  
devenv /updateconfiguration  
```  
  
## <a name="remarks"></a>备注  
 安装 VSIX 包时，[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 会自动运行此命令。 应在修补文件后运行 `devenv.exe /updateconfiguration`，以便 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 更新 MEF 缓存。 这样便于评估是否进行了适当的修补。  
  
## <a name="example"></a>示例  
 以下命令行会使 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 合并系统上的 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 包，并检查 MEF 缓存中是否有任何更改。  
  
```  
Devenv.exe /updateconfiguration  
```  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)



