---
title: IDebugApplication::StepOutComplete |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.StepOutComplete
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::StepOutComplete
ms.assetid: 9675b214-7be5-4cf7-a63f-7865f3c54371
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1798d347fff11a49b945519fd20c370eca75d590
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089916"
---
# <a name="idebugapplicationstepoutcomplete"></a>IDebugApplication::StepOutComplete
通知进程调试管理器中单步执行模式的语言引擎即将返回给调用方。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT StepOutComplete();  
```  
  
#### <a name="parameters"></a>参数  
 此方法需要任何参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 语言引擎调用此方法在单步执行模式下，它们返回到其调用方之前。 进程调试管理器可利用此机会来通知他们应在第一次机会处分的所有其他脚本引擎。 此技术是如何跨语言步骤模式的实现。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplication 接口](../../winscript/reference/idebugapplication-interface.md)