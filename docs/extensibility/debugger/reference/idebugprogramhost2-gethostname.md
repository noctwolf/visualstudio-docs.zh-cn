---
title: IDebugProgramHost2::GetHostName |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramHost2::GetHostName
helpviewer_keywords:
- IDebugProgramHost2::GetHostName
ms.assetid: 48bbb089-e59a-471a-9965-24b42a8dabf3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 139c7c991235f57dba670c15721751dca71c550f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogramhost2gethostname"></a>IDebugProgramHost2::GetHostName
获取标题、 友好名称或此程序的宿主进程的文件名。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetHostName(   
   DWORD dwType,  
   BSTR* pbstrHostName  
);  
```  
  
```csharp  
int GetHostName(   
   uint dwType,  
   out string pbstrHostName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwType`  
 [in]取值范围为[GETHOSTNAME_TYPE](../../../extensibility/debugger/reference/gethostname-type.md)枚举。  
  
 `pbstrHostName`  
 [out]返回宿主进程的请求的名称。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 在此方法的典型实现`dwType`将忽略参数并返回主机计算机的友好名称。 另一个可能的实现是将传递`dwType`的调用的参数[GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)方法要获取的名称。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)   
 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)