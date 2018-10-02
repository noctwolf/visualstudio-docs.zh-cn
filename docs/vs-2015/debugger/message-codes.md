---
title: 消息代码 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d995a884b8d223a4415549739c9701fd72886a56
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468774"
---
# <a name="message-codes"></a>消息代码
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[消息代码](https://docs.microsoft.com/visualstudio/debugger/message-codes)。  
  
每个消息行中所示[消息视图](../debugger/messages-view.md)包含 P、 的的或 R 代码。 这些代码的含义如下：  
  
|代码|含义|  
|----------|-------------|  
|P|消息被发布到的队列**PostMessage**函数。 提供关于该消息的最终处置任何信息不。|  
|S|消息已发送**SendMessage**函数。 这意味着，发件人不会重新获得控制直到接收方处理，并返回该消息。 接收方可以因此，将返回值传递回发件人。|  
|秒|已发送消息，但安全策略禁止访问返回的值。|  
|R|每个的行都具有相应的 R （返回） 行，其中列出了消息的返回值。 有时被嵌套的消息调用，这意味着，一个消息处理程序将发送另一条消息。|



