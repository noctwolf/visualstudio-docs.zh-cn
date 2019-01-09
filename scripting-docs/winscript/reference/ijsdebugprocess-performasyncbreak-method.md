---
title: 'Ijsdebugprocess:: Performasyncbreak 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugProcess.PerformAsyncBreak
apilocation:
- jscript9diag.dll
ms.assetid: 2a6ee369-ea99-4332-8521-a1741ccb6292
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a614bbfdde117ba223ca3f8f3d8b9b77c44c4393
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089136"
---
# <a name="ijsdebugprocessperformasyncbreak-method"></a>IJsDebugProcess::PerformAsyncBreak 方法
将脚本引擎放入中断模式会导致它为在下一个脚本指令发生中断。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT PerformAsyncBreak(  
   DWORD threadId  
);  
```  
  
#### <a name="parameters"></a>参数  
 `threadId`  
 [in]线程 id。  
  
## <a name="return-value"></a>返回值  
  
## <a name="requirements"></a>要求  
 **标头：** jscript9diag.h  
  
## <a name="see-also"></a>请参阅  
 [IJsDebugProcess 接口](../../winscript/reference/ijsdebugprocess-interface.md)