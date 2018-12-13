---
title: 如何： 查看脚本文档 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Script Explorer
ms.assetid: 8b621e53-4508-4b4a-9995-70995b0b9ac8
caps.latest.revision: 25
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ede19ada6509bd4473ac2455fbe6cd9fdf5ec8b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51735687"
---
# <a name="how-to-view-script-documents"></a>如何：查看脚本文档
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 的早期版本中，从服务器端脚本生成的客户端脚本文件显示在“脚本资源管理器”窗口中。 “脚本资源管理器”窗口通常是隐藏的，因此客户端脚本的可用性并非总是显而易见。  
  
 在 [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] 中，从服务器端脚本生成的客户端脚本文件显示在解决方案资源管理器中，后者默认情况下是可见的。 已经放弃了“脚本资源管理器”窗口。  
  
 客户端脚本文件仅在调试模式或中断模式下显示。 它们显示在**脚本文档**节点。  
  
 服务器端脚本文件始终可见。 它们显示在**\<网站路径名 >** 节点。 节点的名称类似于以下示例： `c:\...\Website2\`  
  
### <a name="to-view-a-server-side-script-document"></a>查看服务器端脚本文档  
  
1.  在中**解决方案资源管理器**，打开**\<网站路径名 >** 节点。  
  
2.  双击要查看的脚本文件。  
  
     服务器端脚本文件在源窗口中打开。  
  
### <a name="to-view-a-client-side-script-document"></a>查看客户端脚本文档  
  
1.  在中**解决方案资源管理器**，打开**脚本文档**节点。  
  
2.  双击要查看的脚本文件。  
  
     客户端脚本文件在源窗口中打开。  
  
## <a name="see-also"></a>请参阅  
 [查看调试器中的数据](../debugger/viewing-data-in-the-debugger.md)



