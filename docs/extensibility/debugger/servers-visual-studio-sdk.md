---
title: 服务器 (Visual Studio SDK) |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- servers, debugging
- debugging [Debugging SDK], servers
ms.assetid: 62236d64-7956-448c-9ac3-5528f3edac1d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2904641e8188abc6ef2382b2da272a9f96fd0f81
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31125487"
---
# <a name="servers-visual-studio-sdk"></a>服务器 (Visual Studio SDK)
在调试器体系结构，方面**服务器**:  
  
-   是的端口和端口提供容器，用于与会话调试管理器 (SDM) 通信端口和端口供应商和调试引擎。  
  
-   可以按名称、 标识自身，并枚举其端口和端口供应商。  
  
-   由[IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md)接口，仅实现由 Visual Studio （的 Visual Studio 运行每个实例的服务器的一个实例）。  
  
## <a name="see-also"></a>另请参阅  
 [端口](../../extensibility/debugger/ports.md)   
 [端口供应商](../../extensibility/debugger/port-suppliers.md)   
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md)