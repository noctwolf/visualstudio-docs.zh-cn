---
title: ResumeTracking | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
apiname: ResumeTracking
apilocation: filetracker.dll
apitype: COM
helpviewer_keywords: ResumeTracking
ms.assetid: d637e019-7c50-4b0a-812e-bc822001e697
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ae79812a700f8444002ae3b8c04c0ea816970eea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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