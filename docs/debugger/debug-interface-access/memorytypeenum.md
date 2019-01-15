---
title: MemoryTypeEnum |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MemoryTypeEnum enumeration
ms.assetid: 8778c047-edeb-4495-8f9f-3f8bbb297099
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a83a37a3aa454885d714be667ca7678ae543ff09
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53875911"
---
# <a name="memorytypeenum"></a>MemoryTypeEnum
指定要访问的内存的类型。  
  
## <a name="syntax"></a>语法  
  
```C++  
enum MemoryTypeEnum {  
   MemTypeCode,  
   MemTypeData,  
   MemTypeStack,  
   MemTypeAny = -1  
};  
```  
  
#### <a name="parameters"></a>参数  
 `MemTypeCode`  
 访问仅代码的内存。  
  
 `MemTypeData`  
 访问数据或堆栈内存。  
  
 `MemTypeStack`  
 访问仅堆栈内存。  
  
 `MemTypeAny`  
 访问任何类型的内存。  
  
## <a name="remarks"></a>备注  
 此枚举中的值传递给[IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)方法，以限制对不同类型的内存访问。  
  
## <a name="requirements"></a>要求  
 标头： cvconst.h  
  
## <a name="see-also"></a>请参阅  
 [枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)