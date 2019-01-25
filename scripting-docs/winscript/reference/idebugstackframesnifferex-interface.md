---
title: IDebugStackFrameSnifferEx 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugStackFrameSnifferEx interface
ms.assetid: fd6cf744-dee7-45f2-9a90-355b90372923
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76f10d6bbb34c61e87a1be0f61dcd7db168274e7
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348485"
---
# <a name="idebugstackframesnifferex-interface"></a>IDebugStackFrameSnifferEx 接口
提供了一种方法来枚举逻辑堆栈帧已知的组件。 脚本引擎通常情况下实现此接口。 此接口以查找所有堆栈帧进程调试管理器使用与给定线程相关联。  
  
> [!NOTE]
>  此接口是从所需的线程内调用的。 接口实现必须识别当前线程，并返回相应的枚举器。  
  
 除了继承的方法之外`IDebugStackFrameSniffer`，则`IDebugStackFrameSnifferEx`接口公开以下方法。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IDebugStackFrameSnifferEx::EnumStackFramesEx](../../winscript/reference/idebugstackframesnifferex-enumstackframesex.md)|返回当前线程的堆栈帧的枚举器。|