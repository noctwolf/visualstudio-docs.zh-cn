---
title: 消息选项卡上，消息选项对话框 |Microsoft Docs
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
- message options, Messages
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8048c63ed9b9f049ed171002dfcc612fc9361569
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479275"
---
# <a name="messages-tab-message-options-dialog-box"></a>“消息选项”对话框 ->“消息”选项卡
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[消息选项卡上，消息选项对话框](https://docs.microsoft.com/visualstudio/debugger/messages-tab-message-options-dialog-box)。  
  
使用**消息**选项卡以选择列表中的消息类型[消息视图](../debugger/messages-view.md)，并指定消息搜索条件。 若要显示[消息选项对话框](../debugger/message-options-dialog-box.md)，选择**日志消息**从**Spy**菜单。  
  
 通常情况下，首先选择**消息组**，然后通过选择单个微调所选内容**查看的消息**。 **所有**按钮选择所有消息类型，并**None**按钮将清除所有类型。  
  
 以下设置位于**消息**选项卡：  
  
 **查看的消息**  
 选择要查看的特定消息。 在创建新的消息窗口时，它可以显示所有消息。 筛选来自消息时**消息**选项卡上，该筛选器仅适用于新消息，不均已显示在 Windows 视图中的消息。  
  
 **消息组**  
 选择消息组进行查看。 可用组包括：  
  
-   使用代码大于或等于 WM_USER WM_USER:  
  
-   注册： 注册**RegisterWindowMessage**调用  
  
-   未知： 范围 0 到 (WM_USER – 1) 中的未知的消息  
  
 请注意，这些**消息组**不会映射到下的特定项**查看的消息**。 当选择一个组时，所选内容将直接应用到消息流。  
  
 中的灰色的复选框**消息组**指示**查看的消息**为该组中的消息，已修改列表框中; 不是所有在该组中的消息类型选择。  
  
 **将设置保存为默认值**  
 将以供将来使用的当前设置保存为消息搜索选项。 退出 Spy + + 时，还会保存这些设置。


