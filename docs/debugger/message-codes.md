---
title: 消息代码 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7c1f568ead3e5862460d4ae4e18e51687737d4a5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53866291"
---
# <a name="message-codes"></a>消息代码
每个消息行中所示[消息视图](../debugger/messages-view.md)包含 P、 的的或 R 代码。 这些代码的含义如下：  
  
|代码|含义|  
|----------|-------------|  
|P|消息被发布到的队列**PostMessage**函数。 提供关于该消息的最终处置任何信息不。|  
|S|消息已发送**SendMessage**函数。 这意味着，发件人不会重新获得控制直到接收方处理，并返回该消息。 接收方可以因此，将返回值传递回发件人。|  
|秒|已发送消息，但安全策略禁止访问返回的值。|  
|R|每个的行都具有相应的 R （返回） 行，其中列出了消息的返回值。 有时被嵌套的消息调用，这意味着，一个消息处理程序将发送另一条消息。|