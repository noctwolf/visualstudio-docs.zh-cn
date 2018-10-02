---
title: IEnumDebugPortSuppliers2 |Microsoft Docs
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
- IEnumDebugPortSuppliers2
helpviewer_keywords:
- IEnumDebugPortSuppliers2
ms.assetid: cd0a73dc-dd25-46fd-8c4f-5b011501afeb
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c85119dc705ee171979467c453b771e3cea65237
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483564"
---
# <a name="ienumdebugportsuppliers2"></a>IEnumDebugPortSuppliers2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IEnumDebugPortSuppliers2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugportsuppliers2)。  
  
此接口枚举端口提供程序。  
  
## <a name="syntax"></a>语法  
  
```  
IEnumDebugPortSuppliers2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 Visual Studio 实现此接口来表示端口供应商提供的列表。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)来获取端口供应商提供的列表。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IEnumDebugPortSuppliers2`。  
  
|方法|描述|  
|------------|-----------------|  
|[下一篇](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-next.md)|检索指定的数目的枚举序列中的端口提供程序。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-skip.md)|跳过枚举序列中的端口供应商提供的指定的数目。|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-reset.md)|将枚举序列重置到开头。|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-clone.md)|创建一个包含当前枚举数形式的相同枚举状态的枚举器。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-getcount.md)|获取一个枚举器中的端口供应商提供的数量。|  
  
## <a name="remarks"></a>备注  
 调试引擎通常不会不需要获取此接口。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)

