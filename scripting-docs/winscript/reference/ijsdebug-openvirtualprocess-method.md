---
title: 'Ijsdebug:: Openvirtualprocess 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJSDebug.OpenVirtualProcess
apilocation:
- jscript9diag.dll
ms.assetid: 5612bf1b-a4e3-4eaf-ac5e-c2e1f147c395
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: daa5414153ee55a431294afaf7b167ee91839bfc
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093985"
---
# <a name="ijsdebugopenvirtualprocess-method"></a>IJsDebug::OpenVirtualProcess 方法
用于创建新虚拟过程对象的工厂方法。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT OpenVirtualProcess(  
   DWORD processId,  
   UINT64 runtimeJsBaseAddress,  
   IJsDebugDataTarget *pDataTarget,  
   IJsDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a>参数  
 `processId`  
 [in]若要附加到调试器的进程 Id。  
  
 `runtimeJsBaseAddress`  
 [in]JavaScript 运行时加载到目标进程的基址。  
  
 `pDataTarget`  
 [in]调试器提供的接口查询进程的状态。  
  
 `ppProcess`  
 [out]新的调试进程对象  
  
## <a name="return-value"></a>返回值  
  
## <a name="remarks"></a>备注  
 如果 Jscript9diag 和 Jscript9 不匹配，则返回 E_JsDEBUG_MISMATCHED_RUNTIME。  
  
## <a name="requirements"></a>要求  
 **标头：** jscript9diag.h  
  
## <a name="see-also"></a>请参阅  
 [IJsDebug 接口](../../winscript/reference/ijsdebug-interface.md)