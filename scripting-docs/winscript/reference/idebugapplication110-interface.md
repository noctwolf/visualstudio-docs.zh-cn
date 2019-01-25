---
title: IDebugApplication110 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110 Interface
ms.assetid: ae943133-eb65-4ddc-a29f-9280a82dd8d6
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b13208d6a507ea4ed3157606f358b6b0168180cf
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349551"
---
# <a name="idebugapplication110-interface"></a>IDebugApplication110 接口
`IDebugApplication110`接口扩展的功能[IDebugApplication 接口](../../winscript/reference/idebugapplication-interface.md)。 您可以对的实现调用 QueryInterface 来获取此接口的实例[IDebugApplication 接口](../../winscript/reference/idebugapplication-interface.md)。  
  
> [!IMPORTANT]
>  此接口由 PDM v11.0 和更高版本实现。 在 activdbg100.h 中发现。  
  
## <a name="methods"></a>方法  
 `IDebugApplication110` 接口公开以下方法。  
  
|方法|描述|  
|------------|-----------------|  
|[IDebugApplication110::SynchronousCallInMainThread](../../winscript/reference/idebugapplication110-synchronouscallinmainthread.md)|将主线程上同步调用。|  
|[IDebugApplication110::AsynchronousCallInMainThread](../../winscript/reference/idebugapplication110-asynchronouscallinmainthread.md)|在主线程上进行异步调用。|  
|[IDebugApplication110::CallableWaitForHandles](../../winscript/reference/idebugapplication110-callablewaitforhandles.md)|等待任何指定的句柄，以向发出信号，同时允许跨线程调用发布到此线程。 必须从调试器线程调用此方法。|