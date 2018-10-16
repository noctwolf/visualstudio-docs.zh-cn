---
title: IEnumDebugObjects |Microsoft Docs
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
- IEnumDebugObjects
helpviewer_keywords:
- IEnumDebugObjects interface
ms.assetid: 0950364c-6c8a-4b6c-ba37-c6aa359fa72c
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cda417c487bfdcfdc5dee21bd95a1664d9249066
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49289999"
---
# <a name="ienumdebugobjects"></a>IEnumDebugObjects
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

> [!IMPORTANT]
>  在 Visual Studio 2015 中，这种方式实现表达式计算器已弃用。 有关实现 CLR 表达式计算器的信息，请参阅[CLR 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)并[托管表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。  
  
 此接口表示的对象实现的集合[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)接口。  
  
## <a name="syntax"></a>语法  
  
```  
IEnumDebugObjects : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 表达式计算器实现此接口可提供的实现的对象集[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)接口。 请注意，这不是由于存在一个标准 COM 枚举[GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md)方法。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)返回此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 此接口实现以下方法。  
  
|方法|描述|  
|------------|-----------------|  
|[下一篇](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)|检索下一套[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)枚举中的对象。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugobjects-skip.md)|将跳过指定的数目的条目。|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugobjects-reset.md)|将枚举重置为第一个条目。|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugobjects-clone.md)|检索当前枚举的副本。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md)|检索枚举中的条目数。|  
  
## <a name="remarks"></a>备注  
 此接口允许对一的数组中的对象进行枚举的调试引擎。  
  
## <a name="requirements"></a>要求  
 标头： ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)

