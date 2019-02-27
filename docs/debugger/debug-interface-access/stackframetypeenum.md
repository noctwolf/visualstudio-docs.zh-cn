---
title: StackFrameTypeEnum | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- StackFrameTypeEnum enumeration
ms.assetid: 61e40163-eee0-4c1f-af47-cef3771bdc41
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 44f715c4f74d9b120b324e2d68417a24c9b42684
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602450"
---
# <a name="stackframetypeenum"></a>StackFrameTypeEnum
指定的堆栈帧类型。

## <a name="syntax"></a>语法

```C++
enum StackFrameTypeEnum {
    FrameTypeFPO,
    FrameTypeTrap,
    FrameTypeTSS,
    FrameTypeStandard,
    FrameTypeFrameData,
    FrameTypeUnknown = -1
};
```

## <a name="elements"></a>元素
`FrameTypeFPO` 帧指针省略;FPO 信息可用。

`FrameTypeTrap` 内核陷阱帧。

`FrameTypeTSS` 内核陷阱帧。

`FrameTypeStandard` 标准 EBP 堆栈帧。

`FrameTypeFrameData` 帧指针省略;帧数据信息可用。

`FrameTypeUnknown` 不具有任何调试信息的帧。

## <a name="remarks"></a>备注
此枚举中的值返回通过调用[idiastackframe:: Get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)方法。

## <a name="requirements"></a>要求
标头： cvconst.h

## <a name="see-also"></a>请参阅
- [枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaStackFrame::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)
