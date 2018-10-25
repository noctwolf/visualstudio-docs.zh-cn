---
title: IDebugProcessSecurity::GetUserName |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f13d7597877104613f0e6ef6380abf0b6bc2a594
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49891461"
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