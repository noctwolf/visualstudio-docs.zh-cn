---
title: IDebugModule2::GetInfo |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugModule2::GetInfo
helpviewer_keywords:
- GetInfo method
- IDebugModule2::GetInfo method
ms.assetid: de337e66-294f-4ac9-b21e-71fac7418e36
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 859a85b51e83d438ea4051e2506c2dc0696768b8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49820676"
---
# <a name="idebugmodule2getinfo"></a>IDebugModule2::GetInfo
获取有关此模块的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetInfo(   
   MODULE_INFO_FIELDS dwFields,  
   MODULE_INFO*       pInfo  
);  
```  
  
```cpp  
int GetInfo(   
   enum_MODULE_INFO_FIELDS dwFields,  
   MODULE_INFO[]           pInfo  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwFields`  
 [in]中的标志的组合[MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)枚举，用于指定的哪些字段`pInfo`要填写。  
  
 `pInfo`  
 [in、 out]一个[MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)使用模块的说明填充的结构。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)结构中包含的模块中显示的名称**模块**窗口。  
  
## <a name="see-also"></a>请参阅  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)