---
title: ResumeTracking | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- ResumeTracking
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- ResumeTracking
ms.assetid: d637e019-7c50-4b0a-812e-bc822001e697
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 47d565bde6ef6211589e9293996c7a651ffdd8bd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477770"
---
# <a name="resumetracking"></a>ResumeTracking
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[ResumeTracking](https://docs.microsoft.com/visualstudio/msbuild/resumetracking)。  
  
  
在当前上下文中恢复跟踪。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT WINAPI ResumeTracking();  
```  
  
## <a name="return-value"></a>返回值  
 [HRESULT] (<!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->) 与 [SUCCEEDED] (<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->) 跟踪恢复位组。 [E_FAIL](<!-- TODO: review code entity reference <xref:assetId:///E_FAIL?qualifyHint=False&amp;autoUpgrade=True>  -->) 如果无法恢复跟踪，因为上下文不可用而返回。  
  
## <a name="requirements"></a>要求  
 标头：FileTracker.h  
  
## <a name="see-also"></a>请参阅  
 [SuspendTracking](../msbuild/suspendtracking.md)



