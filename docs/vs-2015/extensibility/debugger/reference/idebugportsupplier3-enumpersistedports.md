---
title: IDebugPortSupplier3::EnumPersistedPorts |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
helpviewer_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
ms.assetid: 1c3dead3-5d6c-4067-8418-4015f0b0dd07
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8f821c72259a77618c6cd83fe6df84837e21a6db
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470811"
---
# <a name="idebugportsupplier3enumpersistedports"></a>IDebugPortSupplier3::EnumPersistedPorts
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugPortSupplier3::EnumPersistedPorts](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportsupplier3-enumpersistedports)。  
  
此方法检索一个对象，允许的保留端口的列表的枚举。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumPersistedPorts(  
   BSTR_ARRAY         PortNames,  
   IEnumDebugPorts2** ppEnum  
);  
```  
  
```csharp  
int EnumPersistedPorts(  
   BSTR_ARRAY           PortNames,  
   out IEnumDebugPorts2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `PortNames`  
 [in]一个[BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)结构，其中包含要查找并返回在持久化端口之间的端口名称的列表。 将返回与这些名称仅这些持久化的端口。  
  
 `ppEnum`  
 [out]实现的对象[IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 端口提供程序实例化，并保存时销毁端口提供程序时加载持久化的端口。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)   
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)   
 [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)

