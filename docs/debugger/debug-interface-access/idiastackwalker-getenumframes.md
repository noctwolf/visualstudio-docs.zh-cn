---
title: IDiaStackWalker::getEnumFrames |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker2::getEnumFrames method
ms.assetid: f9f09729-4c34-441c-989c-e0b7339ee32c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9011f0becd893fa4ca966c40013844b0be47e46d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56629386"
---
# <a name="idiastackwalkergetenumframes"></a>IDiaStackWalker::getEnumFrames
检索 x86 堆栈帧枚举器的平台。

## <a name="syntax"></a>语法

```C++
HRESULT getEnumFrames( 
   IDiaStackWalkHelper*   pHelper,
   IDiaEnumStackFrames**  ppEnum
);
```

#### <a name="parameters"></a>参数
 `pHelper`

[in]帮助者[IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)对象。

 `ppEnum`

[out]返回[IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md)对象，其中包含一系列[IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)对象。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 若要获取任何其他平台上的堆栈帧列表，请调用[IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)方法。

## <a name="see-also"></a>请参阅
- [IDiaStackWalker](../../debugger/debug-interface-access/idiastackwalker.md)
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
- [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)