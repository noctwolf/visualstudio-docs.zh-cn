---
title: IJsDebugStackWalker 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 3fe30394-49c8-48e9-bde9-ffe5d79b2121
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d79950c6d5595a0a8a95623a7510c5523f16e41b
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087889"
---
# <a name="ijsdebugstackwalker-interface"></a>IJsDebugStackWalker 接口
表示指定线程的堆栈查看器。  
  
## <a name="syntax"></a>语法  
  
```cpp
IJsDebugStackWalker : public IUnknown;  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[IJsDebugStackWalker::GetNext 方法](../../winscript/reference/ijsdebugstackwalker-getnext-method.md)|获取下一个帧。|  
  
## <a name="remarks"></a>备注  
 堆栈查看器只能在目标已停止，而一旦目标进程继续重新创建。  
  
## <a name="requirements"></a>要求  
 **标头：** jscript9diag.h  
  
## <a name="see-also"></a>请参阅  
 [Windows 脚本接口参考](../../winscript/reference/windows-script-interfaces-reference.md)