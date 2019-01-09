---
title: IDebugApplication::StartDebugSession |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.StartDebugSession
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::StartDebugSession
ms.assetid: 737f8424-bbcf-473f-9cf1-6601b9aa250d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 453286e310a6f16576d947cceb1947945f8627d3
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086476"
---
# <a name="idebugapplicationstartdebugsession"></a>IDebugApplication::StartDebugSession
启动默认调试器集成的开发环境 (IDE)，并将调试会话附加到此应用程序，如果尚未附加。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT StartDebugSession();  
```  
  
#### <a name="parameters"></a>参数  
 此方法需要任何参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法用于实现在实时调试。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplication 接口](../../winscript/reference/idebugapplication-interface.md)