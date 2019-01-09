---
title: IDebugApplication::DebugOutput |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.DebugOutput
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::DebugOutput
ms.assetid: 6c02939c-3c2d-474a-ab15-49a37e22b4a7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a4c67567b4dc4df74b43d8003104e8f47455b5f5
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095402"
---
# <a name="idebugapplicationdebugoutput"></a>IDebugApplication::DebugOutput
会导致调试器集成的开发环境 (IDE) 将显示给定的字符串。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT DebugOutput(  
   LPCOLESTR  pstr  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pstr`  
 [in]若要在调试器中显示的字符串。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法允许语言引擎实现特定于语言的调试输出支持。 该字符串通常显示在调试器的输出窗口中。  
  
 此方法将导致`IApplicationDebugger::onDebugOutput`调用。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplication 接口](../../winscript/reference/idebugapplication-interface.md)   
 [IApplicationDebugger::onDebugOutput](../../winscript/reference/iapplicationdebugger-ondebugoutput.md)