---
title: 消息枚举器 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- message enumerator
- source control plug-ins, message enumeration
ms.assetid: 4a4faa0d-d352-40ea-a21d-c09ea286a8e1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 37932ce6e64361692d659355e9ab6e88ee5462ed
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56713173"
---
# <a name="message-enumerator"></a>消息枚举器
以下标志用于`TEXTOUTPROC`函数，这是 IDE 提供了时，它调用的回调函数[SccOpenProject](../extensibility/sccopenproject-function.md) (请参阅[LPTEXTOUTPROC](../extensibility/lptextoutproc.md)有关回调的详细信息函数）。

 如果系统询问 IDE 将取消该过程，它可能会收到一个取消消息。 在这种情况下，源代码管理插件用`SCC_MSG_STARTCANCEL`询问 IDE 以显示**取消**按钮。 在此之后，可能会发送任何一组普通消息。 如果任何这些返回`SCC_MSG_RTN_CANCEL`，则该插件会退出该操作并返回。 该插件还轮询`SCC_MSG_DOCANCEL`定期以确定用户已取消操作。 完成的所有操作，或如果用户已取消，插件会发送时`SCC_MSG_STOPCANCEL`。 `SCC_MSG_INFO`，SCC_MSG_WARNING，和 SCC_MSG_ERROR 类型用于获取消息的滚动列表中显示的消息。 `SCC_MSG_STATUS` 是一种特殊类型，该值指示文本应该出现在状态栏或临时显示区域中。 它不会保持永久列表中。

## <a name="syntax"></a>语法

```
enum { 
   SCC_MSG_RTN_CANCEL = -1, 
   SCC_MSG_RTN_OK = 0, 
   SCC_MSG_INFO = 1 
   SCC_MSG_WARNING, 
   SCC_MSG_ERROR, 
   SCC_MSG_STATUS, 
   SCC_MSG_DOCANCEL, 
   SCC_MSG_STARTCANCEL, 
   SCC_MSG_STOPCANCEL 
};
```

## <a name="members"></a>成员
 SCC_MSG_RTN_CANCEL 从回调返回，这表示取消。

 SCC_MSG_RTN_OK 返回从回调以继续。

 SCC_MSG_INFO 消息仅供参考。

 SCC_MSG_WARNING 消息是一个警告。

 SCC_MSG_ERROR 消息是错误的。

 SCC_MSG_STATUS 消息适用于状态栏。

 SCC_MSG_DOCANCEL 否文本;返回 IDE`SCC_MSG_RTN_OK`或`SCC_MSG_RTN_CANCEL`。

 SCC_MSG_STARTCANCEL 启动一个取消的循环。

 SCC_MSG_STOPCANCEL 停止取消循环。

## <a name="see-also"></a>请参阅
- [源代码管理插件](../extensibility/source-control-plug-ins.md)
- [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)