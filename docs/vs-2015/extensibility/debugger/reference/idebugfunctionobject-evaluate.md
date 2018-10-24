---
title: IDebugFunctionObject::Evaluate |Microsoft Docs
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
- IDebugFunctionObject::Evaluate
helpviewer_keywords:
- IDebugFunctionObject::Evaluate method
ms.assetid: 29349ea3-d5c1-4135-aa76-ced073ab9683
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3eafb749a71c7dc9e6163bd60a8c5c4d2396de32
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49835797"
---
# <a name="idebugfunctionobjectevaluate"></a>IDebugFunctionObject::Evaluate
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

调用函数，并返回结果值作为对象。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Evaluate(   
   IDebugObject** ppParams,  
   DWORD          dwParams,  
   DWORD          dwTimeout,  
   IDebugObject** ppResult  
);  
```  
  
```csharp  
int Evaluate(  
   IDebugObject[]   ppParams,   
   IntPtr           dwParams,   
   uint             dwTimeout,   
   out IDebugObject ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppParams`  
 [in]一个数组[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)表示输入的参数的对象。 其中每个参数之一创建`Create`中的方法[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)接口。  
  
 `dwParams`  
 [in]中的参数数量`ppParams`数组。  
  
 `dwTimeout`  
 [in]指定以毫秒为单位，此方法返回前等待的最长时间。 使用`INFINITE`无限期等待。  
  
 `ppResult`  
 [out]返回[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)表示函数作为对象的值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法将设置，执行对所表示的函数的调用[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)对象。  
  
## <a name="see-also"></a>请参阅  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)

