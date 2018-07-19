---
title: EndTrackingContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- EndTrackingContext
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- EndTrackingContext
ms.assetid: c2c5d794-8dc8-4594-8717-70dc79a0e75d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3bf8720efab88556092e6552a8ffa47cb1151fef
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37946376"
---
# <a name="endtrackingcontext"></a>EndTrackingContext
结束当前跟踪上下文。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT WINAPI EndTrackingContext();  
```  
  
## <a name="return-value"></a>返回值  
 如果跟踪上下文结束，返回带 SUCCEEDED 位组的 HRESULT。  
  
## <a name="requirements"></a>要求  
 标头：FileTracker.h  
  
## <a name="see-also"></a>请参阅  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)