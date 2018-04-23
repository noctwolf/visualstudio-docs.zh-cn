---
title: 消息选项卡，消息选项对话框 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
helpviewer_keywords:
- message options, Messages
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f19da533d2ab13e7493eae53af8dea3af4e520df
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="messages-tab-message-options-dialog-box"></a>“消息选项”对话框 ->“消息”选项卡
使用**消息**选项卡以选择的消息类型列表中[消息视图](../debugger/messages-view.md)，并且可以指定消息搜索条件。 若要显示[消息选项对话框](../debugger/message-options-dialog-box.md)，选择**日志消息**从**Spy**菜单。  
  
 通常，首先选择**消息组**，，然后通过选择各个进行微调所选内容**查看的消息**。 **所有**按钮选择所有的消息类型，与**无**按钮将清除所有类型。  
  
 以下设置子网上有**消息**选项卡：  
  
 **查看的消息**  
 选择要查看特定消息。 在创建新的消息窗口时，它可以显示所有消息。 当筛选来自消息**消息**选项卡上，该筛选器仅适用于新消息，不均已显示在窗口视图中的消息。  
  
 **消息组**  
 选择消息组进行查看。 可用的组包括：  
  
-   WM_USER： 与代码大于或等于 WM_USER  
  
-   注册： 注册**RegisterWindowMessage**调用  
  
-   范围是 0 (WM_USER-1) 到未知： 未知的消息  
  
 请注意，这些**消息组**不映射到下的特定项**查看的消息**。 当你选择一个组时，选择将直接应用到消息流。  
  
 中的灰色的复选框**消息组**指示**查看的消息**为该组中的消息，列表框中已修改; 不是所有该组中的消息类型选择。  
  
 **将设置保存为默认值**  
 将以供将来使用的当前设置保存为消息搜索选项。 退出 Spy + + 时，还会保存这些设置。