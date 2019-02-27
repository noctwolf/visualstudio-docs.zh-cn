---
title: 'Idiastackwalkframe:: Searchforreturnaddressstart |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::searchForReturnAddressStart method
ms.assetid: 47660b9b-6e4f-4dfa-88ab-63dce28f7412
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bf7de77016f5ccc15f2cea8bf3172321dd824096
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640748"
---
# <a name="idiastackwalkframesearchforreturnaddressstart"></a>IDiaStackWalkFrame::searchForReturnAddressStart
搜索指定的堆栈帧的寄信人地址处或附近指定的地址。

## <a name="syntax"></a>语法

```C++
HRESULT searchForReturnAddressStart ( 
   IDiaFrameData* frame,
   ULONGLONG      startAddress,
   ULONGLONG*     returnAddress
);
```

#### <a name="parameters"></a>参数
 `frame`

[in][IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)对象，表示当前堆栈帧。

 `startAddress`

[in]从此处开始搜索的虚拟内存地址。

 `returnAddress`

[out]返回最接近的函数返回地址`startAddress`。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)