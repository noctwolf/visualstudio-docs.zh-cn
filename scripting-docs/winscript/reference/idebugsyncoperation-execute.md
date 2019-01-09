---
title: IDebugSyncOperation::Execute |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugSyncOperation.Execute
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugSyncOperation::Execute
ms.assetid: a45b8c7d-c51a-4098-877f-fbec2f1f6947
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d8c10973bddef45321b9942afef05a696010433f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090215"
---
# <a name="idebugsyncoperationexecute"></a>IDebugSyncOperation::Execute
以同步方式执行该操作并返回。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Execute(  
   IUnknown**  ppunkResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppunkResult`  
 [out]该操作返回的对象参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
|`E_ABORT`|通过调用中止了此操作`IDebugSyncOperation::InProgressAbort`方法。|  
  
## <a name="remarks"></a>备注  
 进程调试管理器中的目标线程调用`Execute`方法以同步方式。  
  
## <a name="see-also"></a>请参阅  
 [IDebugSyncOperation 接口](../../winscript/reference/idebugsyncoperation-interface.md)