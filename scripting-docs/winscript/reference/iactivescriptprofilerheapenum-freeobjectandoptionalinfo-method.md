---
title: 'Iactivescriptprofilerheapenum:: Freeobjectandoptionalinfo 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fdd5f7cc-be4e-4c13-a181-6320d26b44eb
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8dd2b827deba31af1958842cf0dacd2a85f4260d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095688"
---
# <a name="iactivescriptprofilerheapenumfreeobjectandoptionalinfo-method"></a>IActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo 方法
释放指定[PROFILER_HEAP_OBJECT 结构](../../winscript/reference/profiler-heap-object-structure.md)结构和与其相关联[PROFILER_HEAP_OBJECT_OPTIONAL_INFO 结构](../../winscript/reference/profiler-heap-object-optional-info-structure.md)元素。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT FreeObjectAndOptionalInfo (    [in] ULONG celt,    [in, size_is(celt)] PROFILER_HEAP_OBJECT** heapObjects);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 若要释放的对象数。  
  
 `heapObjects`  
 一个数组[PROFILER_HEAP_OBJECT 结构](../../winscript/reference/profiler-heap-object-structure.md)结构。  
  
## <a name="return-value"></a>返回值  
 HRESULT。