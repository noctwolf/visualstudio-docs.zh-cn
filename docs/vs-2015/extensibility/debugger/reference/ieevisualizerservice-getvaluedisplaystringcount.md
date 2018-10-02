---
title: IEEVisualizerService::GetValueDisplayStringCount |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IEEVisualizerService::GetValueDisplayStringCount
- GetValueDisplayStringCount
ms.assetid: d683a833-fbfb-4042-84df-6905124a268a
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4bcf1eae6d948b40cc64f5eadf1c2b3e5a0fd206
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470680"
---
# <a name="ieevisualizerservicegetvaluedisplaystringcount"></a>IEEVisualizerService::GetValueDisplayStringCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IEEVisualizerService::GetValueDisplayStringCount](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ieevisualizerservice-getvaluedisplaystringcount)。  
  
检索要显示为指定的属性或字段的值字符串数。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetValueDisplayStringCount (  
   DWORD         displayKind,   
   IDebugField * propertyOrField,   
   ULONG *       pcelt  
);  
```  
  
```csharp  
int GetValueDisplayStringCount (  
   uint        displayKind,   
   IDebugField propertyOrField,   
   out ulong   pcelt  
);  
```  
  
#### <a name="parameters"></a>参数  
 `displayKind`  
 [in]值从[DisplayKind](../../../extensibility/debugger/reference/displaykind.md)枚举。  
  
 `propertyOrField`  
 [in][IDebugField](../../../extensibility/debugger/reference/idebugfield.md)表示属性或字段的接口。  
  
 `pcelt`  
 [out]返回要显示的值字符串数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)

