---
title: 如何： 视图和 XML 编辑器之间切换 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb69fbbd-d99c-439e-9498-5df9050f8df0
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d739f9923c3686995508d56391513cdd503f5c94
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469112"
---
# <a name="how-to-switch-between-views-and-the-xml-editor"></a>如何：在视图和 XML 编辑器之间切换
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 交换机之间视图和 XML 编辑器](https://docs.microsoft.com/visualstudio/xml-tools/how-to-switch-between-views-and-the-xml-editor)。  
  
  
本主题演示如何在 XML 架构设计器（XSD 设计器）视图和 XML 编辑器之间进行切换。 此示例使用[采购订单架构](../xml-tools/sample-xsd-file-simple-schema.md)。  
  
### <a name="to-switch-between-the-views-and-the-xml-editor"></a>在视图和 XML 编辑器之间切换  
  
1.  若要创建和编辑新的 XML 架构文件，请按照中的步骤[如何： 创建和编辑 XSD 架构文件](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)。  
  
2.  若要从 XML 编辑器中切换到 XML 架构设计器中，右键单击任意位置在 XML 编辑器中，然后选择**视图设计器**。  
  
3.  若要切换到使用水印的图形视图，请单击**使用关系图视图来查看节点之间的关系**起始视图上的链接。  
  
4.  将 `USAddress` 节点从 XML 架构资源管理器拖动到图形视图上。 右键单击`USAddress`在关系图视图中，选择节点**在内容模型视图中显示**的上下文菜单中。  
  
     将显示包含 `USAddress` 节点详细信息的内容模型视图。  
  
5.  若要使用工具栏从内容模型视图切换到起始视图，请单击 XSD 工具栏上的“起始视图”按钮。  
  
6.  若要使用热键在视图之间切换，可按 Ctrl+1 切换到起始视图，按 Ctrl+2 切换到图形视图，按 Ctrl+3 切换到内容模型视图。  
  
7.  若要从内容模型视图转到 XML 编辑器中，右键单击节点并选择**查看代码**的上下文菜单中。



