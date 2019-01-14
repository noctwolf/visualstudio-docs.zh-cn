---
title: WriteAllTLogs | Microsoft Docs
ms.date: 11/04/2016
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
ms.openlocfilehash: 4ca5bfbdae319aff8d90686deb32a5c7348fa74e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53985532"
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
 **标头：** FileTracker.h  
  
## <a name="see-also"></a>请参阅  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)