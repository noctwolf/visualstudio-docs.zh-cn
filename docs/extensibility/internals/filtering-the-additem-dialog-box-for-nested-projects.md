---
title: "筛选嵌套项目 AddItem 对话框 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filtering, nested projects
- nested projects, AddItem dialog box filtering
ms.assetid: 5b3e352e-7f18-4f66-be16-b0ad55637ce5
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e1f5fc7695df028330d0e53faebefc178f499da1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="filtering-the-additem-dialog-box-for-nested-projects"></a>筛选嵌套项目 AddItem 对话框
当显示**AddItem**嵌套的项目，父项目的对话框中可以控制哪些项将显示在对话框中。  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>接口，可筛选的节点都将在**AddItem**对话框。 当子项目显示**AddItem**对话框中，可以实现父`IVsFilterAddProjectItemDlg`否则将显示在子项目的接口和筛选器项。  
  
 在项目特定的父项目下的函数进行分组，你可以实现`IVsFilterAddProjectItemDlg`当用户选择**添加项目项**中嵌套的项目的快捷菜单上。 实现`IvsFilterAddProjectItemDlg displays`仅项目项或文件特定于该组。 即使它们存储在同一个目录，对的其他组的项目项会从对话框中，筛选掉。  
  
 当用户打开**AddItem**对话框中的子，父项目实现`IVsFilterAddProjectItemDlg`接口称为。  
  
 `IVsFilterAddProjectItemDlg`接口还可以实现按类别筛选。 有关详细信息，请参阅[将项添加到添加新项对话框](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)和[注册项目和项模板](../../extensibility/internals/registering-project-and-item-templates.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [将项添加到添加新项对话框](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [注册项目和项模板](../../extensibility/internals/registering-project-and-item-templates.md)   
 [嵌套项目](../../extensibility/internals/nesting-projects.md)