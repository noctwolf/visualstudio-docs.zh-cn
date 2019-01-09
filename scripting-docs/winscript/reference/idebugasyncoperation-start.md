---
title: IDebugAsyncOperation::Start |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugAsyncOperation.Start
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugAsyncOperation::Start
ms.assetid: a7272364-28e0-48ae-8405-b8bce8a6b9fd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 099e256496278a33ccae77351641cfdd23447b1f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094778"
---
# <a name="idebugasyncoperationstart"></a>IDebugAsyncOperation::Start
将导致异步操作以开始。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Start(  
   IDebugAsyncOperationCallBack*  padocb  
);  
```  
  
#### <a name="parameters"></a>参数  
 `padocb`  
 接收来自此操作的状态事件回调接口。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
|`E_UNEXPECTED`|操作已处于挂起状态。|  
  
## <a name="remarks"></a>备注  
 此方法将导致`IDebugSyncOperation::Execute`获取从线程中异步调用`IDebugSyncOperation::GetTargetThread`。 调用此方法应只从在调试程序线程中;否则，它将不返回直到完成该操作。  
  
## <a name="see-also"></a>请参阅  
 [IDebugAsyncOperation::Abort](../../winscript/reference/idebugasyncoperation-abort.md)   
 [IDebugAsyncOperation 接口](../../winscript/reference/idebugasyncoperation-interface.md)   
 [IDebugSyncOperation::Execute](../../winscript/reference/idebugsyncoperation-execute.md)   
 [IDebugSyncOperation::GetTargetThread](../../winscript/reference/idebugsyncoperation-gettargetthread.md)