---
title: CvReleaseProvider 函数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvReleaseProvider
helpviewer_keywords:
- CvReleaseProvider method
ms.assetid: 8d74379e-295d-452b-bd5f-0769df387d4f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f0b54fc676a9e7e6ee523bba7f94f58aef49916b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="cvreleaseprovider-function"></a>CvReleaseProvider 函数
发布标记提供程序。 发布标记提供程序不会影响此提供程序以前创建的标记系列。 标记系列必须由 CvReleaseMarkerSeries 调用单独发布。 提供程序发布失败会导致内存泄漏。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CvReleaseProvider(  
   _In_ PCV_PROVIDER pProvider  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pProvider`  
 提供程序上下文。 不能为 NULL。  
  
## <a name="return-value"></a>返回值  
 成功发布提供程序时返回 S_OK，出现任何错误时返回错误代码。 使用 SUCCEEDED/FAILED 宏检查错误条件。  
  
## <a name="requirements"></a>惠?  
 **标头：**cvmarkers.h  
  
## <a name="see-also"></a>请参阅  
 [C++ 库参考](../profiling/cpp-library-reference.md)