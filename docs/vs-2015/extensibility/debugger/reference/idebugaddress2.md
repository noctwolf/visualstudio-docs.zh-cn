---
title: IDebugAddress2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugAddress2
helpviewer_keywords:
- IDebugAddress2 interface
ms.assetid: b150e0ed-4ac0-4f8c-9732-4b3e54b9d243
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 23fb27643a209e870165e521d63079a3b6c650eb
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58932353"
---
# <a name="idebugaddress2"></a>IDebugAddress2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此接口提供访问该对象所属的地址的进程 ID 表示通过此接口。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugAddress2 : IDebugAddress  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 符号提供程序实现此接口上实现的相同对象[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)接口。 此接口提供对拥有此地址与相关的对象的进程的 ID 的访问。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 使用[QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3)若要获取此接口从[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 除了继承的方法之外[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)接口，此接口实现了以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetProcessID](../../../extensibility/debugger/reference/idebugaddress2-getprocessid.md)|检索拥有该接口表示的对象的进程的 ID。|  
  
## <a name="requirements"></a>要求  
 标头： sh.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [符号提供程序接口](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
