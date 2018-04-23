---
title: 消息代码 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 25b2061d9f20da8e9c4d5b4f9794f400d638260c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="message-codes"></a>消息代码
中显示每个消息行[消息视图](../debugger/messages-view.md)包含 P、 的的或 R 代码。 这些代码的含义如下：  
  
|代码|含义|  
|----------|-------------|  
|P|消息传递到的队列**PostMessage**函数。 提供关于消息的最终处置不了任何信息。|  
|S|消息已发送**SendMessage**函数。 这意味着，发件人无法重新获得控制权直到接收方处理，并将该消息返回。 接收方可以因此，将返回值传递回发件人。|  
|秒|消息已发送，但安全可防止对返回的值的访问。|  
|R|每个的行都具有相应的 R （回车） 行，其中列出了消息返回值。 有时消息调用被嵌套，这意味着该一条消息处理程序发送一条消息。|