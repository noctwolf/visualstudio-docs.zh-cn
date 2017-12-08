---
title: JsRuntimeHandle Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3c0344e203c58691048c55ba4080c6c86c1c643
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="jsruntimehandle-typedef"></a>JsRuntimeHandle Typedef
Chakra 运行时的句柄。  
  
## <a name="syntax"></a>语法  
  
```  
typedef void *JsRuntimeHandle;  
```  
  
## <a name="remarks"></a>备注  
 每个 Chakra 运行时都有自己独立的执行引擎、JIT 编译器和以及垃圾回收堆。 因此，每个运行时都完全独立于其他运行时。  
  
 运行时可在任意线程上使用，但任何时候只有一个线程能调入运行时。  
  
> [!WARNING]
>  与 Chakra 托管 API 中的其他对象引用不同，JsRuntimeHandle 不会作为垃圾回收，因为它本身包含垃圾回收堆。 运行时将继续存在，直到 JsDisposeRuntime 被调用。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)