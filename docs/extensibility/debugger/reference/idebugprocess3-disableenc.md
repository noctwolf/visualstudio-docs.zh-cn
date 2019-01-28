---
title: IDebugProcess3::DisableENC | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProcess3::DisableENC
helpviewer_keywords:
- IDebugProcess3::DisableENC
ms.assetid: cffdbdac-4d76-4aeb-aa55-5d0410db99f1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 967f795ad79cc8d1803bc2ab4af13fd0c17c9190
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55025470"
---
# <a name="idebugprocess3disableenc"></a>IDebugProcess3::DisableENC
此方法显式禁用编辑并继续此过程 （和其包含的所有程序）。 自定义端口提供程序应始终返回`E_NOTIMPL`。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DisableENC(  
   EncUnavailableReason reason  
);  
```  
  
```csharp  
   EncUnavailableReason reason  
);  
```  
  
#### <a name="parameters"></a>参数  
 `reason`  
 [in]中的值[EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)枚举。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为将返回错误代码。  
  
> [!NOTE]
>  自定义端口提供程序应始终返回`E_NOTIMPL`。  
  
## <a name="remarks"></a>备注  
 一次编辑并继续禁用的进程，它可以重新启用仅通过重新启动进程。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)