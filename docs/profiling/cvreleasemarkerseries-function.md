---
title: CvReleaseMarkerSeries 函数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvReleaseMarkerSeries
helpviewer_keywords:
- CvReleaseMarkerSeries method
ms.assetid: 3b4711ee-e534-411d-9128-f69cd7932a48
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 27c5bbc5d47972a4829c4e46f6aafdcf8ee76fad
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749354"
---
# <a name="cvreleasemarkerseries-function"></a>CvReleaseMarkerSeries 函数
发布标记系列。 在发布之后请勿使用标记系列对象，否则应用程序可能会崩溃。 标记系列发布失败会导致内存泄漏。  
  
## <a name="syntax"></a>语法  
  
```C  
HRESULT CvReleaseMarkerSeries(  
   _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pMarkerSeries`  
 提供程序对象变量的地址。 地址不能为 NULL，该变量可以具有任何值。  
  
## <a name="return-value"></a>返回值  
 成功发布标记系列时返回 S_OK，出现任何错误时返回错误代码。 使用 SUCCEEDED/FAILED 宏检查错误条件。  
  
## <a name="requirements"></a>要求  
 **标头：** cvmarkers.h  
  
## <a name="see-also"></a>请参阅  
 [C++ 库参考](../profiling/cpp-library-reference.md)