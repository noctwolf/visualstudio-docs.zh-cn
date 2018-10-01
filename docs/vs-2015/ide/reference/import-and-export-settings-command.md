---
title: “导入和导出设置”命令 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Tools.ImportandExportSettings
helpviewer_keywords:
- Tools.ImportandExportSettings
- Import and Export Settings command
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e4a638686bb0ec111bf551cac0b38bb5d50b1774
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471352"
---
# <a name="import-and-export-settings-command"></a>“导入和导出设置”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[导入和导出设置命令](https://docs.microsoft.com/visualstudio/ide/reference/import-and-export-settings-command)。  
  
  
导入、导出或重置 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 设置。  
  
## <a name="syntax"></a>语法  
  
```  
Tools.ImportandExportSettings [/export:filename | /import:filename | /reset]  
```  
  
## <a name="switches"></a>开关  
 /export:`filename`  
 可选。 将当前设置导出到指定文件。  
  
 /import:`filename`  
 可选。 导入指定文件中的设置。  
  
 /reset  
 可选。 重置当前设置。  
  
## <a name="remarks"></a>备注  
 不带任何开关运行此命令将打开“导入和导出设置”向导。 有关详细信息，请参阅[如何：在计算机之间或 Visual Studio 各版本之间共享设置](http://msdn.microsoft.com/en-us/1131fb10-35c1-42da-9cd8-91aa3235b882)。  
  
## <a name="example"></a>示例  
 以下命令将当前设置导出到文件 `MyFile.vssettings`。  
  
```  
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"  
```  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)



