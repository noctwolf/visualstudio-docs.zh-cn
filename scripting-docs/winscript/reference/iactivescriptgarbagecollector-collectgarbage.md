---
title: IActiveScriptGarbageCollector::CollectGarbage | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 75f77c49-2190-4d49-a3e0-9dcf847c502b
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: db8683534e449b2cdd8fcdb344c245d93da8fafc
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144662"
---
# <a name="iactivescriptgarbagecollectorcollectgarbage"></a>IActiveScriptGarbageCollector::CollectGarbage
活动脚本主机调用此方法来启动垃圾收集。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT CollectGarbage(        SCRIPTGCTYPE scriptgctype    );  
```  
  
#### <a name="parameters"></a>参数  
 `scriptgctype`  
 [in][SCRIPTGCTYPE 枚举](../../winscript/reference/scriptgctype-enumeration.md)，指定是否为正常或详尽的垃圾回收。  
  
## <a name="return-value"></a>返回值  
 返回一个 HRESULT。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptGarbageCollector 接口](../../winscript/reference/iactivescriptgarbagecollector-interface.md)