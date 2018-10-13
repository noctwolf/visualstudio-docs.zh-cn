---
title: IDebugProgram2::Terminate |Microsoft Docs
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
- IDebugProgram2::Terminate
helpviewer_keywords:
- IDebugProgram2::Terminate
ms.assetid: 4d3127d3-b1e9-4b28-ac22-2f2eea255f86
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1d7e43ba54b7efae0d66ace43821e8736663136e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49286593"
---
# <a name="idebugprogram2terminate"></a>IDebugProgram2::Terminate
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

终止程序。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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

