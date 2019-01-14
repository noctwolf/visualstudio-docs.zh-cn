---
title: marker_importance 枚举 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_importance
helpviewer_keywords:
- Concurrency::diagnostic::marker_importance enumeration
ms.assetid: d5524ea0-0227-4d8e-9122-332291042df5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 330ba15fa62272bd2c2f7ea7b40d6b527ab237c3
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53841685"
---
# <a name="markerimportance-enumeration"></a>marker_importance 枚举
表示并发可视化工具标记的重要性级别。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum marker_importance;  
```  
  
## <a name="members"></a>成员  
  
### <a name="values"></a>值  
  
|name|说明|  
|----------|-----------------|  
|`critical_importance`|指定该标记具有关键重要性。|  
|`high_importance`|指定该标记具有高重要性。|  
|`low_importance`|指定该标记具有低重要性。|  
|`normal_importance`|指定该标记具有普通重要性。|  
  
## <a name="requirements"></a>要求  
 **标头：** cvmarkersobj.h  
  
 **命名空间：** Concurrency::diagnostic  
  
## <a name="see-also"></a>请参阅  
 [diagnostic 命名空间](../profiling/diagnostic-namespace.md)