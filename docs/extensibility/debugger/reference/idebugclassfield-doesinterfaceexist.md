---
title: IDebugClassField::DoesInterfaceExist |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugClassField::DoesInterfaceExist
helpviewer_keywords:
- IDebugClassField::DoesInterfaceExist method
ms.assetid: cc0c8642-1a76-4fda-a309-7018a34883c9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: adddb92adc7f62d51efd5c87ad40c1f47de41ae7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55040718"
---
# <a name="idebugclassfielddoesinterfaceexist"></a>IDebugClassField::DoesInterfaceExist
确定是否在类中定义的特定接口。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DoesInterfaceExist(   
   LPCOLESTR pszInterfaceName  
);  
```  
  
```csharp  
int DoesInterfaceExist(  
   [In] string pszInterfaceName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszInterfaceName`  
 [in]包含要查找的接口名称的字符串。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK，则返回 S_FALSE 接口不存在; 如果否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 实际上，此方法获取的所有接口的枚举，并搜索匹配的接口的列表。  
  
## <a name="see-also"></a>请参阅  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)