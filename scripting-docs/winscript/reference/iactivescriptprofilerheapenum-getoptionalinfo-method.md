---
title: 'Iactivescriptprofilerheapenum:: Getoptionalinfo 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 99ed9df5-71cf-4c25-b189-af9accc466ee
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bcba1214a0c57e738dec41cdc4976f478802fedc
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088798"
---
# <a name="iactivescriptprofilerheapenumgetoptionalinfo-method"></a>IActiveScriptProfilerHeapEnum::GetOptionalInfo 方法
获取指定对象上的可选信息 (从堆返回的对象从集中[IActiveScriptProfilerControl3::EnumHeap 方法](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md))。  
  
 您不应释放返回的内存分配给返回的对象。 相反，应调用[iactivescriptprofilerheapenum:: Freeobjectandoptionalinfo 方法](../../winscript/reference/iactivescriptprofilerheapenum-freeobjectandoptionalinfo-method.md)。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetOptionalInfo (    [in] PROFILER_HEAP_OBJECT* heapObject,    [in] ULONG celt,    [out, size_is(celt)] PROFILER_HEAP_OBJECT_OPTIONAL_INFO* optionalInfo);  
```  
  
#### <a name="parameters"></a>参数  
 `heapObject`  
 [PROFILER_HEAP_OBJECT 结构](../../winscript/reference/profiler-heap-object-structure.md)要为其返回的信息。  
  
 `celt`  
 数[PROFILER_HEAP_OBJECT_OPTIONAL_INFO 结构](../../winscript/reference/profiler-heap-object-optional-info-structure.md)结构返回。  
  
 `optionalInfo`  
 [out]一个数组[PROFILER_HEAP_OBJECT_OPTIONAL_INFO 结构](../../winscript/reference/profiler-heap-object-optional-info-structure.md)结构指定的对象。  
  
## <a name="return-value"></a>返回值  
 HRESULT。