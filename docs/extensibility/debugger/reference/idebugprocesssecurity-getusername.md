---
title: IDebugProcessSecurity::GetUserName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fd3f7133652cf048bb1b4c7a2e7d4886b1c79a2b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53931085"
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
从端口提供程序获取用户名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetUserName(  
    BSTR *pbstrUserName  
);  
```  
  
```csharp  
int GetUserName (  
    string pbstrUserName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrUserName`  
 [out]包含的用户名称的字符串。  
  
## <a name="return-value"></a>返回值  
 如果此方法成功，它将返回`S_OK`。 否则，它返回一个错误代码。  
  
## <a name="remarks"></a>备注  
 `GetUserName` 返回在显示的用户名**用户名**的列**附加到进程**对话框。 若要查看**附加到进程**对话框中，单击**附加到进程**上**工具**菜单中的[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]集成的开发环境 (IDE)。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)