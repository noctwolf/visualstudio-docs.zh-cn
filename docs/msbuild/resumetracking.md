---
title: ResumeTracking | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- ResumeTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- ResumeTracking
ms.assetid: d637e019-7c50-4b0a-812e-bc822001e697
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9651197d24e96f58551bca5cfde5ec60b25bfa09
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
ms.locfileid: "31577309"
---
# <a name="resumetracking"></a>ResumeTracking
在当前上下文中恢复跟踪。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT WINAPI ResumeTracking();  
```  
  
## <a name="return-value"></a>返回值  
 如果跟踪恢复，则返回带 SUCCEEDED 位集的 HRESULT。 如果因为上下文不可用而无法恢复跟踪，将返回“E_FAIL”。  
  
## <a name="requirements"></a>惠?  
 标头：FileTracker.h  
  
## <a name="see-also"></a>请参阅  
 [SuspendTracking](../msbuild/suspendtracking.md)