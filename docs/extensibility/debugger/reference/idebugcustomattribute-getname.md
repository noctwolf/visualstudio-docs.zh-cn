---
title: IDebugCustomAttribute::GetName |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCustomAttribute::GetName
helpviewer_keywords:
- IDebugCustomAttribute::GetName
ms.assetid: ba509cc5-5816-4925-a094-4c72d88c360c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 11a4b986799cf03221b4af077fc3e1e5809c4137
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49866475"
---
# <a name="idebugcustomattributegetname"></a>IDebugCustomAttribute::GetName
获取自定义特性的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetName(   
   BSTR* bstrName  
);  
```  
  
```csharp  
int GetName(  
   out string bstrName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `bstrName`  
 [out]返回包含自定义特性的名称的字符串。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法返回的命名对应于用于声明属性的类的名称。 这可能不完全对应于自定义特性类本身的名称，如 C# 允许在声明中使用时要删除自定义属性名称从"Attribute"后缀。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)