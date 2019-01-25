---
title: 'Idiaframedata:: Get_type |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_type method
ms.assetid: efca38b5-c479-4d0a-a164-f903f25c5509
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9ee35b5884696d2d9faade5ceb2ec16945d3991c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53837558"
---
# <a name="idiaframedatagettype"></a>IDiaFrameData::get_type
检索特定于编译器的帧类型。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_type (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回一个值从[StackFrameTypeEnum 枚举](../../debugger/debug-interface-access/stackframetypeenum.md)枚举，指示特定于编译器的帧类型。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 `S_OK`。 返回`S_FALSE`如果此属性不受支持。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [StackFrameTypeEnum 枚举](../../debugger/debug-interface-access/stackframetypeenum.md)