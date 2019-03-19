---
title: IDebugApplicationNode100 Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100 Interface
ms.assetid: 43966d4e-5f89-4a04-a08d-782347d00c2d
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f380245422047142b3f06757f6c1057302dd5d26
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58146040"
---
# <a name="idebugapplicationnode100-interface"></a>IDebugApplicationNode100 接口
`IDebugApplicationNode100`接口扩展的功能[IDebugApplicationNode 接口](../../winscript/reference/idebugapplicationnode-interface.md)。 您可以对的实现调用 QueryInterface 来获取此接口的实例[IDebugApplicationNode 接口](../../winscript/reference/idebugapplicationnode-interface.md)。  
  
> [!IMPORTANT]
>  此接口由 PDM 10.0 版及更高版本实现。 在 activdbg100.h 中发现。  
  
## <a name="methods"></a>方法  
 `IDebugApplicationNode100` 接口公开以下方法。  
  
|方法|描述|  
|------------|-----------------|  
|[IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md)|获取指定的筛选器隐藏的文本文档。|  
|[IDebugApplicationNode100::QueryIsChildNode](../../winscript/reference/idebugapplicationnode100-queryischildnode.md)|确定此节点的子节点之一是否属于指定的文档。|  
|[IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)|对特定设置的筛选器[IDebugApplicationNodeEvents 接口](../../winscript/reference/idebugapplicationnodeevents-interface.md)实现。 它允许脚本调试器，若要筛选出编译器生成子应用程序节点，以便 PDM 将不再发送事件时创建或删除节点。 默认情况下，将发送的所有节点。|