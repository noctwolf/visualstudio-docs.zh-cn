---
title: SuspendTracking | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- SuspendTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SuspendTracking
ms.assetid: f5e06e5a-8083-444c-99c1-07ba834226b5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70411d7279dd3f8023971546fd1d228298ce1634
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53911749"
---
# <a name="suspendtracking"></a>SuspendTracking
在当前上下文中暂停跟踪。  
  
## <a name="syntax"></a>语法  
  
```cpp 
HRESULT WINAPI SuspendTracking(void);  
```  
  
## <a name="return-value"></a>返回值  
 如果跟踪暂停，则返回带 SUCCEEDED 位集的 HRESULT。  
  
## <a name="requirements"></a>要求  
 **标头：** FileTracker.h  
  
## <a name="see-also"></a>请参阅  
 [ResumeTracking](../msbuild/resumetracking.md)