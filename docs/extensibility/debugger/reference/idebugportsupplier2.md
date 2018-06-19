---
title: IDebugPortSupplier2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier2
helpviewer_keywords:
- IDebugPortSupplier2 interface
ms.assetid: 37067324-2ea6-4a01-8829-a6e9c7a70068
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e4aa26aa37b40c0e483342e6eb93cbac15bbbfc2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31119469"
---
# <a name="idebugportsupplier2"></a>IDebugPortSupplier2
此接口提供到会话调试管理器 (SDM) 的端口。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugPortSupplier2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 自定义端口供应商提供实现此接口可表示的端口供应商提供。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用`CoCreateInstance`与端口供应商的`GUID`返回此接口 （这是获得此接口的典型方法）。 例如：  
  
```cpp  
IDebugPortSupplier2 *GetPortSupplier(GUID *pPortSupplierGuid)  
{  
    IDebugPortSupplier2 *pPS = NULL;  
    if (pPortSupplierGuid != NULL) {  
        CComPtr<IDebugPortSupplier2> spPortSupplier;  
        spPortSupplier.CoCreateInstance(*pPortSupplierGuid);  
        if (spPortSupplier != NULL) {  
            pPS = spPortSupplier.Detach();  
        }  
    }  
    return (pPS);  
}  
```  
  
 调用[GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)返回此接口，表示当前正在使用的端口供应商[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]。  
  
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)返回此接口，表示创建端口的端口供应商。  
  
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)表示列表`IDebugPortSupplier`接口 (`IEnumDebugPortSuppliers`接口从获取[EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)，表示端口供应商的所有注册到[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]).  
  
 调试引擎通常不与端口提供程序交互。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugPortSupplier2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetPortSupplierName](../../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md)|获取端口供应商名称。|  
|[GetPortSupplierId](../../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)|获取端口供应商标识符。|  
|[GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md)|获取一个端口从端口供应商。|  
|[EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)|枚举已存在的端口。|  
|[CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)|验证的端口供应商提供支持添加新端口。|  
|[添加](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)|将添加一个端口。|  
|[RemovePort](../../../extensibility/debugger/reference/idebugportsupplier2-removeport.md)|删除端口。|  
  
## <a name="remarks"></a>备注  
 端口供应商可以标识自身按名称和 ID、 添加和删除端口，以及枚举端口供应商提供的所有端口。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)   
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)