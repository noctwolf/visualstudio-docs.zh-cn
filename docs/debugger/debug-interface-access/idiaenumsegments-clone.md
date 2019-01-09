---
title: 'Idiaenumsegments:: Clone |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Clone method
ms.assetid: 93deaac6-72ab-4408-ba14-66174a618757
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de7b9b12c17f6a0d9295809551d403b4d490dd94
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53859089"
---
# <a name="idiaenumsegmentsclone"></a>IDiaEnumSegments::Clone
创建一个包含当前枚举数形式的相同枚举状态的枚举器。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Clone (   
   IDiaEnumSegments** ppenum  
);  
```  
  
#### <a name="parameters"></a>参数  
 ppenum  
 [out]返回[IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)对象，其中包含重复的枚举器。 不重复的段，仅枚举器。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)