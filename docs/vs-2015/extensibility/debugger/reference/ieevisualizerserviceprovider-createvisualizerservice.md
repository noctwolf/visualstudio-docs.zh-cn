---
title: IEEVisualizerServiceProvider::CreateVisualizerService |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEEVisualizerServiceProvider::CreateVisualizerService
helpviewer_keywords:
- IEEVisualizerServiceProvider::CreateVisualizerService method
ms.assetid: f366f7c9-358d-46c8-993f-32ff86539833
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6f6bbb0077fcc8dd8d151b995a9c416113e1b5ef
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49243433"
---
# <a name="ieevisualizerserviceprovidercreatevisualizerservice"></a>IEEVisualizerServiceProvider::CreateVisualizerService
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此方法创建可视化工具服务。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateVisualizerService(  
   IDebugBinder*              binder,  
   IDebugSymbolProvider*      pSymProv,  
   IDebugAddress*             pAddress,  
   IEEVisualizerDataProvider* dataProvider,  
   IEEVisualizerService**     ppService  
);  
```  
  
```csharp  
int CreateVisualizerService(  
   IDebugBinder binder,  
   IDebugSymbolProvider      pSymProv,  
   IDebugAddress             pAddress,  
   IEEVisualizerDataProvider dataProvider,  
   out IEEVisualizerService  ppService  
);  
```  
  
#### <a name="parameters"></a>参数  
 `binder`  
 [in][IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)对象传递给[EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)。  
  
 `pSymProv`  
 [in][IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)对象传递给`IDebugParsedExpression::EvaluateSync`。  
  
 `pAddress`  
 [in][IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)对象传递给`IDebugParsedExression::EvaluateSync`。  
  
 `dataProvider`  
 [in]一个对象，实现[IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)接口 （由表达式计算器提供）。  
  
 `ppService`  
 [out]已创建的服务。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 `binder`， `pSymProv`，并`pAddress`参数已传递给`IDebugParsedExpression::EvaluateSync`方法。 `CreateVisualizerService` 是仅从调用`IDebugParsedExpression::EvaluateSync`作为类型可视化工具的表达式计算器支持的一部分。  
  
## <a name="see-also"></a>请参阅  
 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)

