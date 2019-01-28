---
title: IDebugEngine3::SetSymbolPath |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngine3::SetSymbolPath
helpviewer_keywords:
- IDebugEngine3::SetSymbolPath
ms.assetid: 47b48f84-8a96-401f-84df-0baa8a96d26e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c92bdd32c43e3877262bae16011e27eb73963e7a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54932945"
---
# <a name="idebugengine3setsymbolpath"></a>IDebugEngine3::SetSymbolPath
设置搜索的调试符号的路径。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetSymbolPath (  
   LPOLESTR            szSymbolSearchPath,  
   LPOLESTR            szSymbolCachePath,  
   LOAD_SYMBOLS_FLAGS  Flags  
);  
```  
  
```csharp  
int SetSymbolPath(  
   string                    szSymbolSearchPath,   
   string                    szSymbolCachePath,   
   enum_LOAD_SYMBOLS_FLAGS   Flags  
);  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|`szSymbolSearchPath`|[in]包含符号搜索路径的字符串。 有关详细信息，请参阅"备注"。 不能为 null。|  
|`szSymbolCachePath`|[in]包含可以在其中缓存符号的本地路径的字符串。 不能为 null。|  
|`Flags`|[in]未使用;始终设置为 0。|  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则将返回错误代码。  
  
## <a name="remarks"></a>备注  
 字符串`szSymbolSearchPath`是一系列由分号隔开，搜索符号的一个或多个路径。 这些路径可以是本地路径、 UNC 样式路径或 URL。 这些路径也可以是不同类型的组合。 如果该路径是 UNC (例如， \\\Symserver\Symbols)，如果路径是到符号服务器，应该能够从该服务器，它们在缓存中指定的路径加载符号，以调试引擎应确定`szSymbolCachePath`。  
  
 符号路径还可以包含一个或多个缓存位置。 首先，列出按优先级顺序，具有最高优先级缓存并分隔缓存 * 符号。 例如：  
  
```  
\\symbols\symbols;\\someotherserver\symbols;c:\symbols\httpsymbols*http://msdl.microsoft.com  
```  
  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)方法执行实际加载的符号。  
  
## <a name="see-also"></a>请参阅  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)   
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)