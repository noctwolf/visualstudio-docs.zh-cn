---
title: IDebugApplication110 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 3c040df103bac464e4f440f23674da966063f0ae
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58149664"
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