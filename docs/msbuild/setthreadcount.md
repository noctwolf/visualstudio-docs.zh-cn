---
title: SetThreadCount | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
apiname:
- SetThreadCount
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 059c3015bf542dda6a420c80620bc74c9ee6ca6b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
ms.locfileid: "31567221"
---
# <a name="setthreadcount"></a>SetThreadCount
设置全局线程计数，并将该计数分配给当前线程。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT WINAPI SetThreadCount(int threadCount);  
```  
  
#### <a name="parameters"></a>参数  
 [in] `threadCount`  
 要使用的线程数。  
  
## <a name="return-value"></a>返回值  
 线程数更新后，则返回带 SUCCEEDED 位集的 HRESULT。  
  
## <a name="requirements"></a>惠?  
 标头：FileTracker.h