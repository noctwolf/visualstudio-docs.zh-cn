---
title: IDebugAsyncOperationCallBack::onComplete |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugAsyncOperationCallBack.onComplete
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugAsyncOperationCallBack::onComplete
ms.assetid: d4023f5a-41f9-4948-b0dc-3317d61bb783
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4909f469b558ef4664a74c4a7926001d20adc40e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089396"
---
# <a name="idebugasyncoperationcallbackoncomplete"></a>IDebugAsyncOperationCallBack::onComplete
发出信号，结果是可从异步调试操作。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT onComplete();  
```  
  
#### <a name="parameters"></a>参数  
 此方法需要任何参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法向发出信号，结果是可从`IDebugAsyncOperation`对象。 引发该事件的调试程序线程中。  
  
## <a name="see-also"></a>请参阅  
 [IDebugAsyncOperationCallBack 接口](../../winscript/reference/idebugasyncoperationcallback-interface.md)   
 [IDebugAsyncOperation 接口](../../winscript/reference/idebugasyncoperation-interface.md)