---
title: 'VsgDbg:: ~ VsgDbg （析构函数） |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7a3b97fb-d344-4df7-b195-9347d1edfcf7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 64d2ce58a0a543a6bccfca4d96ff57915d45ce49
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686556"
---
# <a name="vsgdbgvsgdbg-destructor"></a>VsgDbg::~VsgDbg（析构函数）
销毁实例`VsgDbg`类。 如果主动记录图形信息时，图形日志文件被终结并被关闭，并释放主动捕获图形信息时使用的资源。

## <a name="syntax"></a>语法

```C++
~VsgDbg();
```

## <a name="see-also"></a>请参阅
- [VsgDbg::VsgDbg（构造函数）](vsgdbg-vsgdbg-constructor.md)