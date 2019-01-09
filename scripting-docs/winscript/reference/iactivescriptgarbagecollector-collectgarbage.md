---
title: IActiveScriptGarbageCollector::CollectGarbage |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 75f77c49-2190-4d49-a3e0-9dcf847c502b
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 478a7a39c69e0c2106e3c6cc308f44f8f7aa3201
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097118"
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