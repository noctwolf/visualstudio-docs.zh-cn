---
title: 空间选项卡上，进程属性对话框 |Microsoft Docs
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
ms.assetid: c4de1866-7447-48f7-aa88-28ad92c0b930
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 78f65edeec910bd0667bfc369ff1d4cbddb54813
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478032"
---
# <a name="space-tab-process-properties-dialog-box"></a>“进程属性”对话框 ->“空间”选项卡
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[空间选项卡上，进程属性对话框](https://docs.microsoft.com/visualstudio/debugger/space-tab-process-properties-dialog-box)。  
  
使用**空间**选项卡可以检查进程的地址空间。 若要显示[进程属性对话框](../debugger/process-properties-dialog-box.md)，将焦点移至[进程视图](../debugger/processes-view.md)窗口。 在树中，选择任何进程节点，然后选择**属性**从**视图**菜单。  
  
 以下设置位于**空间**选项卡：  
  
|条目|描述|  
|-----------|-----------------|  
|**显示标记的空间**|使用此列表框中选择的空间 （图像、 映射、 保留或取消分配） 的类别。|  
|**可执行文件的字节数**|所选的类别，此进程正在使用的地址空间之和。 可执行文件的内存是可以由程序执行，但不是能读取或写入的内存。|  
|**仅限 exec 读取的字节数**|所选的类别，与此进程正在使用的只读属性一起使用的所有地址空间的总和。 仅限 exec 读取内存是指可以执行和读取。|  
|**Exec 读取写入的字节数**|所选的类别，与此进程正在使用的读写属性一起使用的所有地址空间的总和。 Exec 读写内存是可以由程序执行，以及读取和修改的内存。|  
|**Exec 写入副本的字节数**|所选的类别，可以由程序执行，以及读取和写入的地址空间之和。 当需要在不同进程之间共享内存时使用此类型的保护。 如果共享处理只读内存，那么它们全部使用相同的内存。 如果共享进程需要写访问权限，然后将为该进程生成一份此内存。|  
|**不可访问字节数**|所选的类别，禁止使用它的进程的地址空间之和。 如果编写，则会生成访问冲突或尝试读取。|  
|**仅限读取的字节数**|对于所选的类别中，指可以执行和读取的地址空间之和。|  
|**读取写入的字节数**|所选的类别，允许读取和写入的地址空间之和。|  
|**写复制字节**|所选类别的所有地址空间之和允许共享内存进行读取，但不是进行写入。 当进程读取此内存时，它们可以共享相同的内存。 但是，当共享过程需要具有对此共享内存的读/写访问权限，该内存的副本由进行写入。|



