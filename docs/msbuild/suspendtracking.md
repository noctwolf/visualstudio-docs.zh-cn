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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cc2a8b3dc2f5940c64be870df452b088dce7bc0e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56632454"
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
- [ResumeTracking](../msbuild/resumetracking.md)