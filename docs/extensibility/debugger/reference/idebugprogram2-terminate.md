---
title: IDebugProgram2::Terminate | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Terminate
helpviewer_keywords:
- IDebugProgram2::Terminate
ms.assetid: 4d3127d3-b1e9-4b28-ac22-2f2eea255f86
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fad3f8829bb4d455dd09df2a896a1e2cd9daa9e6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54975657"
---
# <a name="idebugprogram2terminate"></a>IDebugProgram2::Terminate
终止程序。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Terminate(   
   void   
);  
```  
  
```csharp  
int Terminate();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果可能，将终止并从进程; 中卸载程序否则，调试引擎 (DE) 将执行任何必要的清理。  
  
 此方法或[Terminate](../../../extensibility/debugger/reference/idebugprocess2-terminate.md) IDE 中，通常以响应停止所有调试用户调用方法。 此方法的实现应，理想情况下，终止过程中的程序。 如果无法做到这一点，DE 应运行此过程中的其他任何阻止程序 （和执行任何必要的清理）。 如果`IDebugProcess2::Terminate`由 IDE 调用方法，将一段时间后终止整个过程`IDebugProgram2::Terminate`调用方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [Terminate](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)