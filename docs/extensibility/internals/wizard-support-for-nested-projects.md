---
title: 嵌套的项目的向导支持 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Add Item wizard
- nested projects, wizard support
- New Project wizard
ms.assetid: 1b496acc-b326-4cdb-bb48-e3b5c6f12e05
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 14e8a32db2542ae1729a7fdc87cc2ab32845f8ca
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31137490"
---
# <a name="wizard-support-for-nested-projects"></a>嵌套的项目的向导支持
IDE 运行嵌套项目的父项目可以实现的两个向导：**新项目**向导和**添加项**向导。  
  
 如果用户启动**新项目**向导通过选择**添加项目**并单击**新项目**文件菜单上或通过选择**添加**右键单击**新项目**在解决方案资源管理器，IDE 将运行**AddProject**命令和父项目实现**AddProject**命令返回模板项目文件中或具有一组上下文参数的向导 (.vsz) 文件。  
  
 同样，父项目的实现**AddItem**向导返回具有一组不同的上下文参数的.vsz 文件。  
  
 有关向导的详细信息，请参阅[向导 (。Vsz) 文件](../../extensibility/internals/wizard-dot-vsz-file.md)，[上下文参数](../../extensibility/internals/context-parameters.md)和[注册项目和项模板](../../extensibility/internals/registering-project-and-item-templates.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [嵌套项目](../../extensibility/internals/nesting-projects.md)