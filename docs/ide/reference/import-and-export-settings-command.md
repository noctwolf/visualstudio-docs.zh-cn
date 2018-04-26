---
title: “导入和导出设置”命令
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
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
ms.openlocfilehash: a95841d9b9b8e67f34883efcc1a55a2daba7e8b7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
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

- [个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)
- [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)