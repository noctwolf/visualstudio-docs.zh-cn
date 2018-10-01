---
title: 引用 （编程捕获） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef60eb8d-1ac2-4e3a-9b4b-f6da0bdd9da8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 70581d468c32964d7e081ec0ee4af3fe411b71b9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479772"
---
# <a name="reference-programmatic-capture"></a>引用（编程捕获）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[引用 （编程捕获）](https://docs.microsoft.com/visualstudio/debugger/graphics/reference-programmatic-capture)。  
  
图形诊断支持通过编程捕获 API 对其捕获功能进行编程控制。 此 API 可用于切换消息和将消息添加到图形诊断 HUD（提醒显示）、初始化和创建图形日志文件以及捕获图形信息。  
  
## <a name="programmatic-capture-apis"></a>编程捕获 API  
  
### <a name="classes"></a>类  
  
|名称|描述|  
|----------|-----------------|  
|[VsgDbg 类](../debugger/vsgdbg-class.md)|表示接口，通过该接口以编程方式控制图形诊断的应用内组件。|  
  
### <a name="preprocessor-symbols"></a>预处理器符号  
  
|name|描述|  
|----------|-----------------|  
|[DONT_SAVE_VSGLOG_TO_TEMP](../debugger/dont-save-vsglog-to-temp.md)|通过其存在定义图形日志文件是否保存到用户的临时文件目录。|  
|[VSG_DEFAULT_RUN_FILENAME](../debugger/vsg-default-run-filename.md)|定义图形日志文件的默认文件名。|  
|[VSG_NODEFAULT_INSTANCE](../debugger/vsg-nodefault-instance.md)|通过其存在定义是否提供了 `VsgDbg` 类的默认实例。|  
  
## <a name="related-articles"></a>相关文章  
  
|标题|描述|  
|-----------|-----------------|  
|[捕获图形信息](../debugger/capturing-graphics-information.md)|演示如何从基于 DirectX 的应用捕获图形信息，以便使用 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 图形诊断工具来诊断呈现问题。|  
|[概述](../debugger/overview-of-visual-studio-graphics-diagnostics.md)|演示图形诊断可如何帮助你调试 DirectX 游戏和应用中的呈现错误。|



