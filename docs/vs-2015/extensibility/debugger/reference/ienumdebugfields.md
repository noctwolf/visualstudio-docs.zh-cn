---
title: IEnumDebugFields |Microsoft Docs
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
- IEnumDebugFields
helpviewer_keywords:
- IEnumDebugFields interface
ms.assetid: 403c2a51-3ba5-431f-a1dd-2f3b2046c00c
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b56a0823ec0c2f02374e46fb8be61277da6adb88
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468553"
---
# <a name="ienumdebugfields"></a>IEnumDebugFields
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IEnumDebugFields](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugfields)。  
  
此接口表示的对象实现的集合[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口。  
  
## <a name="syntax"></a>语法  
  
```  
IEnumDebugFields : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 此接口由符号提供程序来实现的对象集的实现[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口。 请注意，这不是由于存在一个标准 COM 枚举[GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)方法。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 此接口将返回由[GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)并[GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 此接口实现以下方法。  
  
|方法|描述|  
|------------|-----------------|  
|[下一篇](../../../extensibility/debugger/reference/ienumdebugfields-next.md)|检索下一套[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)枚举中的对象。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugfields-skip.md)|将跳过指定的数目的条目。|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugfields-reset.md)|将枚举重置为第一个条目。|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugfields-clone.md)|检索当前枚举的副本。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)|检索枚举中的条目数。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [符号提供程序接口](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)   
 [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)

