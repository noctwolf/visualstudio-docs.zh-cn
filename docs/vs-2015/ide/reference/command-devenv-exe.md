---
title: -Command (devenv.exe) | Microsoft Docs
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
- Devenv, /command switch
- /command Devenv switch
ms.assetid: 13c20cd6-f09d-400a-8b7b-ecc266a32cef
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5f95d8758da77f1b720f0a1b6ca74f7ac753d805
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49254356"
---
# <a name="command-devenvexe"></a>/Command (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
在启动 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 集成开发环境 (IDE) 后执行指定的命令。  
  
## <a name="syntax"></a>语法  
  
```  
devenv /command CommandName  
```  
  
## <a name="arguments"></a>自变量  
 `CommandName`  
 必须的。 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 命令或其别名的完整名称括在双引号内。 有关命令和别名语法的详细信息，请参阅 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)。  
  
## <a name="remarks"></a>备注  
 启动完成后，IDE 将执行已命名的命令。 如果使用此开关，IDE 将不会在启动时显示 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 起始页。  
  
 如果外接程序公开了某个命令，则可以使用此开关从命令行启动此外接程序。 有关详细信息，请参阅[如何：使用外接程序管理器控制外接程序](http://msdn.microsoft.com/library/4f60444a-cb48-4cdb-8df4-941f6419aeeb)。  
  
## <a name="example"></a>示例  
 此示例将启动 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 并自动运行宏“打开收藏夹文件”。  
  
```  
devenv /command "Macros.MyMacros.Module1.OpenFavoriteFiles"  
```  
  
## <a name="see-also"></a>请参阅  
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



