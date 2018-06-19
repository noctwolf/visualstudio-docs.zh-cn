---
title: “选项”对话框 ->“环境”->“自动恢复”
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPag.Environment.AutoRecover
- VS.DialogAutoRestore
- VS.ToolsOptionsPages.Environment.AutoRecover
- VS.ToolsOptionsPages.Environment.Auto_Save_and_Restore
helpviewer_keywords:
- files, recovering
- AutoRecover page
- saving files, automatically
- files, saving automatically
ms.assetid: 397e5e44-4bbe-4289-94d1-642b466c9111
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3f6409e31a606fe31fa1296dc937616338f8d62c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31943197"
---
# <a name="autorecover-environment-options-dialog-box"></a>“选项”对话框 ->“环境”->“自动恢复”
使用选项对话框中的此页可指定是否自动备份文件。 使用此页，还可指定当集成开发环境 (IDE) 意外关闭时是否还原已修改的文件。 要访问此对话框，请依次选择“工具”菜单->“选项”->“环境”文件夹->“自动恢复”页。 如果此页未出现在列表中，请在“选项”对话框中选择“显示所有设置”。

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在“工具”菜单上选择“导入和导出设置”。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)。

 **每 \<n> 分钟保存一次自动恢复信息** 使用此选项可以自定义在编辑器中自动保存文件的频率。 对于以前保存的文件，文件的副本保存在 \\...\My Documents\Visual Studio \<版本>\Backup Files\\<项目名称>。 如果是新文件且尚未手动保存，则将使用一个随机生成的文件名自动保存该文件。

 **将自动恢复信息保留 \<n> 天** 使用此选项可指定 Visual Studio 将为自动恢复创建的文件保留多长时间。

## <a name="see-also"></a>请参阅

- [“选项”对话框](../../ide/reference/options-dialog-box-visual-studio.md)