---
title: “导入和导出设置”命令 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- Tools.ImportandExportSettings
helpviewer_keywords:
- Tools.ImportandExportSettings
- Import and Export Settings command
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ad7da7f8d83cd45e7cc7801d430dbf70887747b3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="import-and-export-settings-command"></a>“导入和导出设置”命令
导入、导出或重置 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 设置。  
  
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

不带任何开关运行此命令将打开“导入和导出设置”向导。 有关详细信息，请参阅[同步设置](../../ide/synchronized-settings-in-visual-studio.md)。

## <a name="example"></a>示例

以下命令将当前设置导出到文件 `MyFile.vssettings`。

```shell
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"
```

## <a name="see-also"></a>请参阅

[个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)  
[Visual Studio 命令](../../ide/reference/visual-studio-commands.md)