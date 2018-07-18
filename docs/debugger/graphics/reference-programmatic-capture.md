---
title: 引用 （编程捕获） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ef60eb8d-1ac2-4e3a-9b4b-f6da0bdd9da8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd6ea361d0cec07e3f1fe1a3d5b6771ec7fcb5d6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474383"
---
# <a name="reference-programmatic-capture"></a>引用（编程捕获）
图形诊断支持通过编程捕获 API 对其捕获功能进行编程控制。 此 API 可用于切换消息和将消息添加到图形诊断 HUD（提醒显示）、初始化和创建图形日志文件以及捕获图形信息。  
  
## <a name="programmatic-capture-apis"></a>编程捕获 API  
  
### <a name="classes"></a>类  
  
|名称|描述|  
|----------|-----------------|  
|[VsgDbg 类](vsgdbg-class.md)|表示接口，通过该接口以编程方式控制图形诊断的应用内组件。|  
  
### <a name="preprocessor-symbols"></a>预处理器符号  
  
|名称|描述|  
|----------|-----------------|  
|[DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)|通过其存在定义图形日志文件是否保存到用户的临时文件目录。|  
|[VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)|定义图形日志文件的默认文件名。|  
|[VSG_NODEFAULT_INSTANCE](vsg-nodefault-instance.md)|通过其存在定义是否提供了 `VsgDbg` 类的默认实例。|  
  
## <a name="related-articles"></a>相关文章  
  
|标题|描述|  
|-----------|-----------------|  
|[Capturing Graphics Information](capturing-graphics-information.md)|演示如何从基于 DirectX 的应用捕获图形信息，以便使用 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 图形诊断工具来诊断呈现问题。|  
|[概述](overview-of-visual-studio-graphics-diagnostics.md)|演示图形诊断可如何帮助你调试 DirectX 游戏和应用中的呈现错误。|