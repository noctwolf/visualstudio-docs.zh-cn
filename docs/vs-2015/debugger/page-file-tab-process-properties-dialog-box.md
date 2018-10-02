---
title: 页面文件选项卡上，进程属性对话框 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: daf41a06-8a55-48f6-95f5-49a8416bd308
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2fa1eba7af60638d82c791958af6bf66a3272242
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481810"
---
# <a name="page-file-tab-process-properties-dialog-box"></a>“进程属性”对话框 ->“页文件”选项卡
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[页文件选项卡中，进程属性对话框](https://docs.microsoft.com/visualstudio/debugger/page-file-tab-process-properties-dialog-box)。  
  
使用**页面文件**选项卡以查看进程的分页文件。 若要显示[进程属性对话框](../debugger/process-properties-dialog-box.md)，将焦点移至[进程视图](../debugger/processes-view.md)窗口。 在树中，选择任何进程节点，然后选择**属性**从**视图**菜单。  
  
 以下设置位于**页面文件**选项卡：  
  
|条目|描述|  
|-----------|-----------------|  
|**页面文件字节数**|此过程使用的分页文件中的页的数目。 分页文件存储过程使用的但不是包含其他文件中的数据的页。 分页文件由所有进程，并且当其他进程正在运行时，在分页文件的空间不足可能会导致错误。|  
|**峰值页文件字节**|此进程已在分页文件中使用最大页数。|  
|**页面错误**|在此过程中执行的线程的页面错误数。 当线程引用不在其工作集中在主内存中的虚拟内存页面，页面错误时发生。 因此，页面将不从磁盘中检索它是否在备用列表上，因此已在主内存中，或如果它正由另一个处理与共享的页面。|



