---
title: WriteAllTLogs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- WriteAllTLogs
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- WriteAllTLogs
ms.assetid: 1fa3e10b-263c-4960-a9ad-485c02a7a872
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ceec441f6f0110ea514225ed0fab4c4dc2d575bb
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2018
ms.locfileid: "39153080"
---
# <a name="writealltlogs"></a>WriteAllTLogs
写入所有线程和上下文的跟踪日志。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT WINAPI WriteAllTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);  
```  
  
#### <a name="parameters"></a>参数  
 [in] `intermediateDirectory`  
 存储跟踪日志的目录。  
  
 [in] `tlogRootName`  
 日志文件名的根名称。  
  
## <a name="return-value"></a>返回值  
 如果跟踪上下文创建完成，则返回带 SUCCEEDED 位集的 HRESULT。  
  
## <a name="requirements"></a>要求  
 标头：FileTracker.h  
  
## <a name="see-also"></a>请参阅  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)