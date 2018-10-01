---
title: IEEVisualizerServiceProvider |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEEVisualizerServiceProvider
helpviewer_keywords:
- IEEVisualizerServiceProvider interface
ms.assetid: 859d1a51-1c65-4c8b-ae74-3b74b181ebcd
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e27eab6c3547790ca1f66181c04bba085e463c5e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469691"
---
# <a name="ieevisualizerserviceprovider"></a>IEEVisualizerServiceProvider
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IEEVisualizerServiceProvider](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ieevisualizerserviceprovider)。  
  
> [!IMPORTANT]
>  在 Visual Studio 2015 中，这种方式实现表达式计算器已弃用。 有关实现 CLR 表达式计算器的信息，请参阅[CLR 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)并[托管表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。  
  
 此接口，可以创建可视化工具服务，用于为在 IDE 中处理类型可视化工具任务的方法访问。  
  
## <a name="syntax"></a>语法  
  
```  
IEEVisualizerServiceProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 Visual Studio 实现此接口来创建可视化工具服务对象，它又用于提供类 Id (`CLSID`s) 的 Visual Studio ide 的类型可视化工具。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 表达式计算器 (EE) 调用[GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md)若要获取此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)|创建可视化工具服务|  
  
## <a name="remarks"></a>备注  
 `IEEVisualizerServiceProvider`的实现过程获取接口[EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)。 此接口创建的可视化工具服务用于提供功能提供给[IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)接口，EE 负责实施。 程序还负责实现 EE [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)接口允许类型可视化工具查看和修改属性的值。  
  
 请参阅[可视化和查看数据](../../../extensibility/debugger/visualizing-and-viewing-data.md)有关这些接口的交互方式的详细信息。  
  
## <a name="requirements"></a>要求  
 标头： ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [表达式计算接口](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [可视化和查看数据](../../../extensibility/debugger/visualizing-and-viewing-data.md)

