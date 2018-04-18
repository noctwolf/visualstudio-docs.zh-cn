---
title: IDiaStackWalker::getEnumFrames |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker2::getEnumFrames method
ms.assetid: f9f09729-4c34-441c-989c-e0b7339ee32c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b57ff6f306cd8725264176d0dd26b7304daf6315
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idiastackwalkergetenumframes"></a>IDiaStackWalker::getEnumFrames
检索的堆栈帧枚举器 x86 平台。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT getEnumFrames(   
   IDiaStackWalkHelper*   pHelper,  
   IDiaEnumStackFrames**  ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pHelper`  
 [in]帮助器[IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)对象。  
  
 `ppEnum`  
 [out]返回[IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md)对象，其中包含一份[IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 若要获取在任何其他平台上的堆栈帧列表，调用[IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)方法。  
  
## <a name="see-also"></a>另请参阅  
 [IDiaStackWalker](../../debugger/debug-interface-access/idiastackwalker.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)