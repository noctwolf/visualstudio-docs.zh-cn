---
title: 如何： 将新项添加到工作流项目 （旧版） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- sequential workflows, adding to workflow projects
- workflows, adding new items
- state machine workflows, adding to workflow projects
- activities, adding to workflow projects
ms.assetid: 130cd83d-942d-437b-bbb5-8088ec0a6d79
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 1a0ccdc10a76f8c8bc594130bcba5210190fb34a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471452"
---
# <a name="how-to-add-a-new-item-to-a-workflow-project-legacy"></a>如何：向工作流项目添加新项（旧版）
在使用 [!INCLUDE[wfd1](../includes/wfd1-md.md)] 提供的、面向 [!INCLUDE[vs2010](../includes/vs2010-md.md)] 或 [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] 的旧 [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] 创建工作流项目之后，可向该项目添加 [!INCLUDE[wf](../includes/wf-md.md)] 项和其他熟悉的 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 项。  
  
 下表列出了可添加到工作流项目中的 [!INCLUDE[wf2](../includes/wf2-md.md)] 项。  
  
|项|描述|  
|----------|-----------------|  
|Activity|活动定义在设计器代码文件中而用户代码在另一个代码文件中的活动。|  
|Activity (具有单独的代码)|位于不同代码文件中的活动定义（以工作流标记形式表示）和用户代码。|  
|顺序工作流 (代码)|工作流定义在设计器代码文件中而用户代码在另一个代码文件中的顺序工作流。|  
|顺序工作流 (具有单独的代码)|工作流定义（以工作流标记形式表示）与用户代码位于不同代码文件中的顺序工作流。|  
|状态机工作流 (代码)|工作流定义在设计器代码文件中而用户代码在另一个代码文件中的状态机工作流。|  
|状态机工作流 (具有单独的代码)|工作流定义（以工作流标记形式表示）与用户代码位于不同代码文件中的状态机工作流。|  
  
### <a name="to-add-a-new-item-to-a-workflow-project"></a>向工作流项目添加新项  
  
1.  上**项目**菜单上，单击**添加新项**。  
  
     **添加新项**对话框随即打开。  
  
2.  选择一个项。  
  
     前面的表列出了可用的 Windows Workflow Foundation 选择。  
  
3.  单击**添加**将项添加到工作流项目。  
  
## <a name="see-also"></a>请参阅  
 [创建旧版工作流项目](../workflow-designer/creating-legacy-workflow-projects.md)