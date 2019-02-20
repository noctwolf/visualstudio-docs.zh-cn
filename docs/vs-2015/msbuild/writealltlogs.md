---
title: WriteAllTLogs | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
api_name:
- WriteAllTLogs
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- WriteAllTLogs
ms.assetid: 1fa3e10b-263c-4960-a9ad-485c02a7a872
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3d5e51a674a075b265aa6ec2550f4e8cf4207c5d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54804749"
---
# <a name="writealltlogs"></a>WriteAllTLogs
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
写入所有线程和上下文的跟踪日志。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT WINAPI WriteAllTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);  
```  
  
#### <a name="parameters"></a>参数  
 [in] `intermediateDirectory`  
 存储跟踪日志的目录。  
  
 [in] `tlogRootName`  
 日志文件名的根名称。  
  
## <a name="return-value"></a>返回值  
 如果曾创建了跟踪上下文，则返回带 [SUCCEEDED](<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->) 位集的 [HRESULT](<!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->)。  
  
## <a name="requirements"></a>要求  
 标头：FileTracker.h  
  
## <a name="see-also"></a>请参阅  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)
