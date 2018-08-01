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
ms.openlocfilehash: 2ec83d60046a74484035df9d7a7831d16b48d899
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151176"
---
# <a name="resumetracking"></a>ResumeTracking
在当前上下文中恢复跟踪。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT WINAPI ResumeTracking();  
```  
  
## <a name="return-value"></a>返回值  
 如果跟踪恢复，则返回带 SUCCEEDED 位集的 HRESULT。 如果因为上下文不可用而无法恢复跟踪，将返回“E_FAIL”。  
  
## <a name="requirements"></a>要求  
 标头：FileTracker.h  
  
## <a name="see-also"></a>请参阅  
 [SuspendTracking](../msbuild/suspendtracking.md)