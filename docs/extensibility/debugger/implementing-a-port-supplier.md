---
title: 实现端口提供程序 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cd068f9c669b898ac3d29dadccffb6edd1e0c783
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53985519"
---
# <a name="implement-a-port-supplier"></a>实现端口提供程序
端口提供程序提供对会话调试管理器 (SDM) 请求上的端口。 向非 DCOM 机或新设备时需要支持进行调试时，必须实现端口提供程序。 例如，若要提供对移动电话调试，你可能会设置端口提供程序提供端口中，它连接到手机 （也许是通过红外线 （ir） 或单元格连接） 和枚举的过程和程序在手机上运行。  
  
 对于基于 Windows 的计算机 （包括远程调试） 上的调试程序，Visual Studio 提供端口供应商的本机和公共语言运行时 (CLR) 的进程，因此无需设置在这些情况下你自己端口提供程序。  
  
## <a name="in-this-section"></a>本节内容  
 [实现和注册端口提供程序](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md)  
 讨论 SDM 与端口提供程序和其端口交互的方式。  
  
 [所需的端口提供程序接口](../../extensibility/debugger/required-port-supplier-interfaces.md)  
 文档必须实现以获取端口提供程序的接口。  
  
## <a name="related-sections"></a>相关章节  
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)  
 描述调试的主要体系结构概念。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 调试器可扩展性](../../extensibility/debugger/visual-studio-debugger-extensibility.md)