---
title: IDiaSession::put_loadAddress | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b768b06e0702f7929b402086dcc6e11918f3e683
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56630088"
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
此符号存储区中的符号设置相对应的可执行文件的加载地址。

## <a name="syntax"></a>语法

```C++
HRESULT put_loadAddress ( 
   ULONGLONG NewVal
);
```

#### <a name="parameters"></a>参数
 `NewVal`

[in]加载可执行文件的地址。

## <a name="remarks"></a>备注
 使用此方法的值计算符号虚拟地址 (VA) 属性。 除非将此属性设置为非零值，不会计算虚拟地址。

> [!NOTE]
>  当你获得时，必须调用此方法[IDiaSession](../../debugger/debug-interface-access/idiasession.md)对象，并开始使用该对象，如果您需要使用任何虚拟属性上的符号之前。

## <a name="see-also"></a>请参阅
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)