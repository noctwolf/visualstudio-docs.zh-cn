---
title: 实现和注册的端口供应商提供 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], registering port suppliers
- port suppliers, registering
ms.assetid: fb057052-ee16-4272-8e16-a4da5dda0ad4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 54d6a4ab90b5ad169c5c940f52322dfd9b4974a4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31103170"
---
# <a name="implementing-and-registering-a-port-supplier"></a>实现和注册端口供应商
端口供应商提供的角色是跟踪并提供反过来管理进程的端口。 在需要创建某个端口时，端口供应商是实例化可以共同创建使用端口供应商的 GUID （端口供应商选定的用户或指定的项目系统端口供应商，将使用会话调试管理器 [SDM]）。 然后将调用 SDM [CanAddPort](../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)以查看是否可以添加任何端口。 如果可以添加一个端口，通过调用请求一个新的端口[添加](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)并将其传递[IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)描述该端口。 `AddPort` 将返回一个新的端口，由表示[IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)接口。  
  
## <a name="discussion"></a>讨论  
 端口供应商，这是与计算机或调试服务器反过来关联创建一个端口。 服务器可以枚举通过其端口供应商[EnumPortSuppliers](../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)方法和端口供应商可以枚举其端口到[EnumPorts](../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)方法。  
  
 除了典型的 COM 注册，端口提供程序必须注册本身 Visual Studio 通过特定的注册表位置中将其 CLSID 和名称。 调试 SDK 帮助器函数调用`SetMetric`处理此烦琐： 它为每个项进行注册，因此一次调用：  
  
```cpp  
SetMetric(metrictypePortSupplier,  
          <GUID of your port supplier>,  
          metricCLSID,  
          <CLSID of your port supplier>,  
          false,  
          NULL)  
SetMetric(metrictypePortSupplier,  
          <GUID of your port supplier>,  
          metricName,  
          <name of your port supplier>,  
          false,  
          NULL);  
```  
  
 通过调用的端口提供程序注销本身`RemoveMetric`（另一个调试 SDK 帮助器函数） 一次针对已注册，因此每个项：  
  
```cpp  
RemoveMetric(metrictypePortSupplier,  
             <GUID of your port supplier>,  
             metricCLSID,  
             NULL);  
RemoveMetric(metrictypePortSupplier,  
             <GUID of your port supplier>,  
             metricName,  
             NULL);  
```  
  
> [!NOTE]
>  [SDK 以便进行调试的帮助器](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)`SetMetric`和`RemoveMetric`是 dbgmetric.h 中定义和编译为 ad2de.lib 的静态函数。 `metrictypePortSupplier`， `metricCLSID`，和`metricName`dbgmetric.h 中也定义帮助器。  
  
 端口供应商可以通过方法提供其名称和 GUID [GetPortSupplierName](../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md)和[GetPortSupplierId](../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)分别。  
  
## <a name="see-also"></a>另请参阅  
 [实现端口供应商](../../extensibility/debugger/implementing-a-port-supplier.md)   
 [SDK 适用于调试的帮助程序](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [端口提供程序](../../extensibility/debugger/port-suppliers.md)