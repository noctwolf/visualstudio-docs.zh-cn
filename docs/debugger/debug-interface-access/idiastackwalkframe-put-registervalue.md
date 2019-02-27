---
title: IDiaStackWalkFrame::put_registerValue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::put_registerValue method
ms.assetid: 2d8b79b6-7240-43fe-b24e-e4ff3e2c15b0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 440c7d19382b813b3f34451d7c177c6e8b57f16f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56613227"
---
# <a name="idiastackwalkframeputregistervalue"></a>IDiaStackWalkFrame::put_registerValue
设置寄存器的值。

## <a name="syntax"></a>语法

```C++
HRESULT put_registerValue ( 
   DWORD     index,
   ULONGLONG NewVal
);
```

#### <a name="parameters"></a>参数
 `index`

[in]中的值[CV_HREG_e 枚举](../../debugger/debug-interface-access/cv-hreg-e.md)枚举，它指定要写入到的寄存器。

 `NewVal`

[in]新的注册值。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)
- [CV_HREG_e 枚举](../../debugger/debug-interface-access/cv-hreg-e.md)