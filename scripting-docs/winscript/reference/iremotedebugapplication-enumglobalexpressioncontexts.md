---
title: IRemoteDebugApplication::EnumGlobalExpressionContexts |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplication.EnumGlobalExpressionContexts
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplication::EnumGlobalExpressionContexts
ms.assetid: 61598a34-f409-42a2-810d-a9e92e2f4861
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a7e4f3e7cffe7c127b7ad4fdde47e58e6bc2a31c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091268"
---
# <a name="iremotedebugapplicationenumglobalexpressioncontexts"></a>IRemoteDebugApplication::EnumGlobalExpressionContexts
枚举此应用程序中运行的所有语言的全局表达式上下文。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT EnumGlobalExpressionContexts(  
   IEnumDebugExpressionContexts**  ppedec  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppedec`  
 [out]列出了此应用程序中运行的所有语言的全局表达式上下文的枚举器。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法枚举此应用程序中运行的所有语言的全局表达式上下文。  
  
## <a name="see-also"></a>请参阅  
 [IRemoteDebugApplication 接口](../../winscript/reference/iremotedebugapplication-interface.md)