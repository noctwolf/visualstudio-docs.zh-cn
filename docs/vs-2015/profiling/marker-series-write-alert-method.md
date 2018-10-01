---
title: marker_series::write_alert 方法 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic:marker_series::write_alert
helpviewer_keywords:
- Concurrency::diagnostic:marker_series::write_alert method
ms.assetid: 9d5465c7-f862-47a7-b249-4116605075a6
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 55623b746ea8eb571ad31337ab252c3d9654f5a5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469939"
---
# <a name="markerserieswritealert-method"></a>marker_series::write_alert 方法
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[marker_series:: write_alert 方法](https://docs.microsoft.com/visualstudio/profiling/marker-series-write-alert-method)。  
  
向并发可视化工具跟踪文件写入一个警报。  
  
## <a name="syntax"></a>语法  
  
```  
void write_alert(  
   _In_ LPCTSTR _Format,  
   ...  
);  
```  
  
#### <a name="parameters"></a>参数  
 `_Format`  
 一个复合格式字符串，其中包含与零个或多个格式项混合的文本，这些格式项对应于参数列表中的对象。  
  
## <a name="requirements"></a>要求  
 **标头：** cvmarkersobj.h  
  
 **命名空间：** Concurrency::diagnostic  
  
## <a name="see-also"></a>请参阅  
 [marker_series 类](../profiling/marker-series-class.md)



