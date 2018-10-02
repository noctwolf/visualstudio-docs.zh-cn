---
title: 嵌套项目的向导支持 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add Item wizard
- nested projects, wizard support
- New Project wizard
ms.assetid: 1b496acc-b326-4cdb-bb48-e3b5c6f12e05
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4621627faae761bfe63b7fd056427a3771d21582
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482901"
---
# <a name="wizard-support-for-nested-projects"></a>嵌套项目的向导支持
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[嵌套项目的向导支持](https://docs.microsoft.com/visualstudio/extensibility/internals/wizard-support-for-nested-projects)。  
  
IDE 将运行两个向导，可以实现嵌套项目的父项目：**新的项目**向导并**添加项**向导。  
  
 如果用户启动**新的项目**向导通过选择**添加项目**，然后单击**新项目**文件菜单或通过选择**添加**右键单击**新的项目**在解决方案资源管理器，IDE 将运行**AddProject**命令和父项目的实施**AddProject**命令返回模板项目文件中或具有组的上下文参数的向导 (.vsz) 文件。  
  
 同样，父项目的实现**AddItem**向导返回具有一组不同的上下文参数的.vsz 文件。  
  
 有关向导的详细信息，请参阅[向导 (。在 Vsz) 文件](../../extensibility/internals/wizard-dot-vsz-file.md)，[上下文参数](../../extensibility/internals/context-parameters.md)并[注册项目和项模板](../../extensibility/internals/registering-project-and-item-templates.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [嵌套项目](../../extensibility/internals/nesting-projects.md)

