---
title: PROFILER_RELATIONSHIP_INFO 枚举 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fae69317-6224-4a6a-8e9e-ccaa6a330818
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e95b11537873d3bfe02bf3fa793b61ace10938aa
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095805"
---
# <a name="profilerrelationshipinfo-enumeration"></a>PROFILER_RELATIONSHIP_INFO 枚举
表示有关对象关系中的信息。 在中使用[PROFILER_HEAP_OBJECT_RELATIONSHIP 结构](../../winscript/reference/profiler-heap-object-relationship-structure.md)。  
  
## <a name="syntax"></a>语法  
  
```cpp
typedef [v1_enum] enum {    PROFILER_PROPERTY_TYPE_NUMBER = 0x01,    PROFILER_PROPERTY_TYPE_STRING = 0x02,    PROFILER_PROPERTY_TYPE_HEAP_OBJECT = 0x03,    PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT = 0x04,    PROFILER_PROPERTY_TYPE_BSTR = 0x05,} PROFILER_RELATIONSHIP_INFO;  
```  
  
## <a name="members"></a>成员  
  
|成员|“值”|描述|  
|------------|-----------|-----------------|  
|PROFILER_PROPERTY_TYPE_NUMBER|0x01|该对象是一个数字。|  
|PROFILER_PROPERTY_TYPE_STRING|0x02|该对象是一个字符串。|  
|PROFILER_PROPERTY_TYPE_HEAP_OBJECT|0x03|对象是堆对象。|  
|PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT|0x04|对象外部，即，不是在垃圾回收堆上。|  
|PROFILER_PROPERTY_TYPE_BSTR|0x05|对象为 BSTR。|  
|PROFILER_PROPERTY_TYPE_SUBSTRING|0x06|对象为子字符串。|