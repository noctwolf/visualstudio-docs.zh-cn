---
title: IDebugEngine3::LoadSymbols |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEngine3::LoadSymbols
helpviewer_keywords:
- IDebugEngine3::LoadSymbols
ms.assetid: c846a440-1d91-4d48-b8f1-82e902ae152b
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7cdb7db24dc31b8cc36d214eb3c78b1a9a233cc7
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49265955"
---
# <a name="idebugengine3loadsymbols"></a>IDebugEngine3::LoadSymbols
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此调试引擎正在调试的所有模块的 （如有必要） 加载符号。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT LoadSymbols();  
```  
  
```csharp  
int LoadSymbols();  
```  
  
#### <a name="parameters"></a>参数  
 无。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则将返回错误代码。  
  
## <a name="remarks"></a>备注  
 这会加载调试符号的引用的此调试引擎的所有模块。 仅当它们尚未加载，还加载符号。 通过调用设置的路径上搜索符号[SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)。  
  
## <a name="see-also"></a>请参阅  
 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)   
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)

