---
title: IDebugDefaultPort2::GetPortNotify | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDefaultPort2::GetPortNotify
helpviewer_keywords:
- IDebugDefaultPort2::GetPortNotify
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 124a901ab00ba06c7855566cda00a3285c2ba6ca
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54974667"
---
# <a name="idebugdefaultport2getportnotify"></a>IDebugDefaultPort2::GetPortNotify
此方法获取[IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)接口为此端口。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetPortNotify(  
   IDebugPortNotify2** ppPortNotify  
);  
```  
  
```csharp  
int GetPortNotify(  
   out IDebugPortNotify2 ppPortNotify  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppPortNotify`  
 [out][IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 通常情况下，`QueryInterface`对象，实现上调用方法[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)接口，以获得[IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)接口。 但是，有一些情况下在不同的对象实现所需的接口。 此方法会隐藏这种情况，并返回`IDebugPortNotify2`中最合适的对象的接口。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)