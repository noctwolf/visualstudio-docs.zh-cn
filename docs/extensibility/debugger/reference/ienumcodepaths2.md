---
title: IEnumCodePaths2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEnumCodePaths2
helpviewer_keywords:
- IEnumCodePaths2 interface
ms.assetid: 17ec9f9e-dc06-4532-b5db-da52efcc8630
caps.latest.revision: 11
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f3da3fbbc8b7ad7dced8a9767b26859cc1a0de1d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ienumcodepaths2"></a>IEnumCodePaths2
此接口表示的代码路径的列表。  
  
## <a name="syntax"></a>语法  
  
```  
IEnumCodePaths2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 调试引擎 (DE) 实现此接口可表示的代码路径的列表。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)获取此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IEnumCodePaths2`。  
  
|方法|描述|  
|------------|-----------------|  
|[下一篇](../../../extensibility/debugger/reference/ienumcodepaths2-next.md)|检索指定的数目的枚举序列中的代码路径。|  
|[Skip](../../../extensibility/debugger/reference/ienumcodepaths2-skip.md)|跳过指定的数目的枚举序列中的代码路径。|  
|[重置](../../../extensibility/debugger/reference/ienumcodepaths2-reset.md)|将枚举序列重置到开头。|  
|[克隆](../../../extensibility/debugger/reference/ienumcodepaths2-clone.md)|创建包含与当前的枚举器相同的枚举状态的枚举。|  
|[GetCount](../../../extensibility/debugger/reference/ienumcodepaths2-getcount.md)|获取枚举器中的代码路径的数量。|  
  
## <a name="remarks"></a>备注  
 代码路径表示在程序中的分支点或函数调用。 代码路径的列表表示通过该代码执行具有所采用的路径。  
  
## <a name="requirements"></a>惠?  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)