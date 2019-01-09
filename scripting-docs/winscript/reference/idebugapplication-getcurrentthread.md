---
title: IDebugApplication::GetCurrentThread |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.GetCurrentThread
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::GetCurrentThread
ms.assetid: 15128e77-6fc6-42a2-8c04-20e22ef03f29
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b0712994881aaa58e41246bc054ba6cee895ae0
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092152"
---
# <a name="idebugapplicationgetcurrentthread"></a>IDebugApplication::GetCurrentThread
返回与当前运行的线程关联的线程。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetCurrentThread(  
   IDebugApplicationThread**  pat  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pat`  
 [out]与当前运行的线程关联的线程。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法返回与当前运行的线程关联的线程。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplication 接口](../../winscript/reference/idebugapplication-interface.md)