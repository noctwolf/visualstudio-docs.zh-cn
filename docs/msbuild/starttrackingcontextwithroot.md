---
title: StartTrackingContextWithRoot | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- StartTrackingContextWithRoot
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StartTrackingContextWithRoot
ms.assetid: f6ef2b76-8035-4a14-8195-aa221c46ef48
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1844901da84c91cc35df18c9867897c634705a39
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
使用指定根标记的响应文件启动跟踪上下文。  
  
## <a name="syntax"></a>语法  
  
```cpp 
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);  
```  
  
#### <a name="parameters"></a>参数  
 [in] `intermediateDirectory`  
 存储跟踪日志的目录。  
  
 [in] `taskName`  
 标识跟踪上下文。 此名称用于创建日志文件名。  
  
 [in] `rootMarkerResponseFile`  
 包含根标记的响应文件的路径名称。 根名称用于将上下文的所有跟踪聚集在一起。  
  
## <a name="return-value"></a>返回值  
 如果跟踪上下文创建完成，则返回带 SUCCEEDED 位集的 HRESULT。  
  
## <a name="requirements"></a>惠?  
 标头：FileTracker.h  
  
## <a name="see-also"></a>请参阅  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)