---
title: IDebugCustomAttribute |Microsoft Docs
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
- IDebugCustomAttribute
helpviewer_keywords:
- IDebugCustomAttribute interface
ms.assetid: c5ae41e9-00b9-4cca-871d-b8de9ef390d1
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c7891e9be85fbac4f01a81e41dd36195f1ec41cc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471358"
---
# <a name="idebugcustomattribute"></a>IDebugCustomAttribute
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugCustomAttribute](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcustomattribute)。  
  
此接口表示一个自定义属性，并可以提供名称、 父级和类类型的属性。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugCustomAttribute : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 符号提供程序实现此接口以支持与符号关联的自定义属性。 它通常在其自己的对象上实现。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[下一步](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md)返回此接口。 调用[EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)方法将返回[IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugCustomAttribute`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetParentField](../../../extensibility/debugger/reference/idebugcustomattribute-getparentfield.md)|获取当前属性附加到的字段。|  
|[GetAttributeTypeField](../../../extensibility/debugger/reference/idebugcustomattribute-getattributetypefield.md)|获取自定义特性类类型。|  
|[GetName](../../../extensibility/debugger/reference/idebugcustomattribute-getname.md)|获取自定义特性的名称。|  
|[GetAttributeBytes](../../../extensibility/debugger/reference/idebugcustomattribute-getattributebytes.md)|获取作为字节的 blob 的属性信息。|  
  
## <a name="remarks"></a>备注  
 自定义属性是适用于 C#，提供与特定的类和方法相关联的自定义元数据的结构。  
  
## <a name="requirements"></a>要求  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [符号提供程序接口](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)

