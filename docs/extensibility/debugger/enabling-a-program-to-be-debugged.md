---
title: 启用要进行调试的程序 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], enabling for programs
ms.assetid: 61d24820-0cd9-48b6-8674-6813f7493237
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ad6e8e9cb8dd34e3cd084bde1eb94ff5774dd4ba
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204383"
---
# <a name="enable-a-program-to-be-debugged"></a>启用要进行调试的程序
在调试引擎 (DE) 可调试的程序之前，必须先启动 DE 或将其附加到现有的程序。  
  
## <a name="in-this-section"></a>本节内容  
 [获取端口](../../extensibility/debugger/getting-a-port.md)  
 讨论如何为启用要进行调试的程序的第一步中获取一个端口。  
  
 [注册程序](../../extensibility/debugger/registering-the-program.md)  
 介绍启用要进行调试的程序的下一步： 注册该端口。 注册后，可以调试程序通过附加或实时 (JIT) 调试的过程。  
  
 [附加到程序](../../extensibility/debugger/attaching-to-the-program.md)  
 介绍了下一步： 将调试器附加到程序。  
  
 [基于启动的附加](../../extensibility/debugger/launch-based-attachment.md)  
 描述为一个程序，这是 SDM 通过启动时自动基于启动的附件。  
  
 [发送所需的事件](../../extensibility/debugger/sending-the-required-events.md)  
 将指导你逐步创建调试引擎 (DE) 时所需的事件并将其附加到的程序。  
  
## <a name="related-sections"></a>相关章节  
 [创建自定义调试引擎](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 定义调试引擎 (DE)，并介绍了通过 DE 接口和如何它们可能会导致不同的操作模式之间进行过渡调试器实现的服务。