---
title: IDebugApplicationNode100::SetFilterForEventSink | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100::SetFilterForEventSink
ms.assetid: cfb34efe-c6e1-4692-8ffd-3ede3a24cd4b
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4b273b770a1d82edbf5bbbe26c0865060234b852
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346483"
---
# <a name="idebugapplicationnode100setfilterforeventsink"></a>IDebugApplicationNode100::SetFilterForEventSink
对特定设置的筛选器[IDebugApplicationNodeEvents 接口](../../winscript/reference/idebugapplicationnodeevents-interface.md)实现。 它允许脚本调试器，若要筛选出编译器生成子应用程序节点，以便 PDM 将不再发送事件时，以下是创建或删除。 默认情况下，将发送的所有节点。  
  
> [!IMPORTANT]
>  [IDebugApplicationNode100 接口](../../winscript/reference/idebugapplicationnode100-interface.md)是实现由 PDM 10.0 版及更高版本。 在 activdbg100.h 中发现。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetFilterForEventSink(        [in] DWORD dwCookie,        [in] APPLICATION_NODE_EVENT_FILTER filter        );  
```  
  
#### <a name="parameters"></a>参数  
 `dwCookie`  
 筛选器的 cookie。  
  
 `filter`  
 筛选器。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplicationNode100 接口](../../winscript/reference/idebugapplicationnode100-interface.md)