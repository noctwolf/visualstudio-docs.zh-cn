---
title: -Upgrade (devenv.exe) | Microsoft Docs
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
- /upgrade Devenv switch
- Devenv, /upgrade switch
- upgrade Devenv switch
ms.assetid: 3468045c-5cc9-4157-9a9d-622452145d27
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 79a00da92ac2da6eb37fa1eef90fa112598d23f3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49264942"
---
# <a name="upgrade-devenvexe"></a>/Upgrade (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
将解决方案文件及其所有项目文件或指定的项目文件更新为这些文件的当前 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 格式。  
  
## <a name="syntax"></a>语法  
  
```  
devenv SolutionFile | ProjectFile /upgrade  
```  
  
## <a name="arguments"></a>自变量  
 `SolutionFile`  
 如果要升级整个解决方案及其项目，则是必需的。 解决方案文件的路径和名称。 可以只输入解决方案文件的名称，也可以输入解决方案文件的完整路径和名称。 如果命名的文件夹或文件尚不存在，将创建该文件夹或文件。  
  
 `ProjectFile`  
 如果要升级单个项目，则是必需的。 解决方案中项目文件的路径和名称。 可以只输入项目文件的名称，也可以输入项目文件的完整路径和名称。 如果命名的文件夹或文件尚不存在，将创建该文件夹或文件。  
  
## <a name="remarks"></a>备注  
 备份文件自动创建并复制到一个名为 Backup 的目录中，该目录是在当前目录中创建的。  
  
 要升级源代码控制的解决方案或项目，必须先将其签出。  
  
 使用 `/upgrade` 开关不会启动 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。 可在解决方案或项目的开发语言的“升级报告”中看到升级结果。 不会返回任何错误或使用情况信息。 有关升级中的项目的详细信息[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]，请参阅[如何： 解决不成功 Visual Studio 项目的升级](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)。  
  
## <a name="example"></a>示例  
 此示例升级 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 解决方案的默认文件夹中名为“MyProject.sln”的解决方案文件。  
  
```  
devenv "MyProject.sln" /upgrade  
```  
  
## <a name="see-also"></a>请参阅  
 [如何： 升级不成功的 Visual Studio 项目进行故障排除](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)   
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)



