---
title: IActiveScriptProfilerControl3 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 64bc860a-54d4-475a-80f6-2f9dba6448ee
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bebe351608b3136ac00a059bffab3535141e7fca
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097131"
---
# <a name="iactivescriptprofilercontrol3-interface"></a>IActiveScriptProfilerControl3 接口
提供的方法来枚举与脚本引擎关联的 GC 堆对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
interface IActiveScriptProfilerControl3 : IActiveScriptProfilerControl2  
```  
  
## <a name="methods"></a>方法  
 [IActiveScriptProfilerControl3::EnumHeap 方法](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)  
 返回的接口 ([IActiveScriptProfilerHeapEnum 接口](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)) 可用于循环访问关联的脚本引擎的上下文中的 GC 堆对象。