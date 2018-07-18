---
title: IEnumDebugCustomAttributes |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumCustomAttributes
helpviewer_keywords:
- IEnumDebugCustomAttributes interface
ms.assetid: 11aa768d-1852-44d6-9de3-17f9bafaded2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1f3387a8243a617fc9120c5caa161912e7aa92fd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31123676"
---
# <a name="ienumdebugcustomattributes"></a>IEnumDebugCustomAttributes
枚举自定义属性。  
  
## <a name="syntax"></a>语法  
  
```  
IEnumCustomAttributes : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 符号提供程序实现此接口以支持自定义特性 (通过[IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)接口)。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 [EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)返回此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IEnumDebugCustomAttributes`。  
  
|方法|描述|  
|------------|-----------------|  
|[下一篇](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md)|检索指定的数目的枚举序列中的自定义属性。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugcustomattributes-skip.md)|跳过指定的数目的枚举序列中的自定义属性。|  
|[重置](../../../extensibility/debugger/reference/ienumdebugcustomattributes-reset.md)|将枚举序列重置到开头。|  
|[克隆](../../../extensibility/debugger/reference/ienumdebugcustomattributes-clone.md)|创建包含与当前的枚举器相同的枚举状态的枚举。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugcustomattributes-getcount.md)|获取枚举器中的自定义的属性数。|  
  
## <a name="requirements"></a>要求  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [符号提供程序接口](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)   
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)