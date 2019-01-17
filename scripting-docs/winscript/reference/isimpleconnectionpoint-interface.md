---
title: ISimpleConnectionPoint 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ISimpleConnectionPoint interface
ms.assetid: f632a82f-942d-4291-963e-e9fa2b162493
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a756fa3f933f4adff56c41a86aee19a0a2a93aa
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346405"
---
# <a name="isimpleconnectionpoint-interface"></a>ISimpleConnectionPoint 接口
用于描述和枚举的特定连接点上触发的事件提供一个简单的方法。 此接口，还可轻松挂接`IDispatch`这些事件的对象。 此接口是实现由进程调试管理器 (PDM)，并使用的脚本引擎。  
  
 此接口是可从`IDebugHelper::CreateSimpleConnectionPoint`。  
  
 除了继承的方法之外`IUnknown`，则`ISimpleConnectionPoint`接口公开以下方法。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[ISimpleConnectionPoint::Advise](../../winscript/reference/isimpleconnectionpoint-advise.md)|建立简单连接点对象和客户端的接收器之间的连接。|  
|[ISimpleConnectionPoint::DescribeEvents](../../winscript/reference/isimpleconnectionpoint-describeevents.md)|在指定范围的事件返回的 DISPID 和每个事件的名称。|  
|[ISimpleConnectionPoint::GetEventCount](../../winscript/reference/isimpleconnectionpoint-geteventcount.md)|返回此接口上公开的事件数。|  
|[ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)|终止先前通过建立的通知连接`ISimpleConnectionPoint::Advise`。|  
  
## <a name="see-also"></a>请参阅  
 [IDebugProperty 接口](../../winscript/reference/idebugproperty-interface.md)