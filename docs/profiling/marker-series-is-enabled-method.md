---
title: marker_series::is_enabled 方法 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_series::is_enabled
helpviewer_keywords:
- Concurrency::diagnostic::marker_series::is_enabled method
ms.assetid: 8ce4dd50-ca29-4c72-98d6-582693f7d501
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0551545835a530ae63d53f8988ef89aab6476293
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2018
---
# <a name="markerseriesisenabled-method"></a>marker_series::is_enabled 方法
确定是否有任何会话启用了该提供程序。  
  
## <a name="syntax"></a>语法  
  
```cpp  
bool is_enabled();  
bool is_enabled(  
   marker_importance _Importance,  
   int _Category  
);  
```  
  
#### <a name="parameters"></a>参数  
 `_Importance`  
 重要性级别。  
  
 `_Category`  
 类别。  
  
## <a name="return-value"></a>返回值  
  
## <a name="requirements"></a>惠?  
 **标头：** cvmarkersobj.h  
  
 **命名空间：** Concurrency::diagnostic  
  
## <a name="see-also"></a>请参阅  
 [marker_series 类](../profiling/marker-series-class.md)