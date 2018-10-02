---
title: IDebugAddress |Microsoft Docs
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
- IDebugAddress
helpviewer_keywords:
- IDebugAddress interface
ms.assetid: bc709ff7-4966-4f36-9af2-690efe2cea1d
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 75a5b1ab9979d7d071282ab4d807d89b5e7abb2b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483165"
---
# <a name="idebugaddress"></a>IDebugAddress
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugAddress](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugaddress)。  
  
此接口表示的项的地址。 它会返回符号处理程序。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugAddress : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 符号提供程序实现此接口来表示对象的地址。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 在多个接口上的很多方法返回此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)|检索[DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)结构描述一个对象和其位置。|  
  
## <a name="remarks"></a>备注  
 符号提供程序返回此接口来表示对象并将其位置 （例如，函数、 方法或类） 在特定范围内。 此接口是从返回并传递给各种方法的符号提供程序和表达式计算器。 通常情况下，符号提供程序是需要解释此接口的内容的唯一实体。  
  
## <a name="requirements"></a>要求  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [符号提供程序接口](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)

