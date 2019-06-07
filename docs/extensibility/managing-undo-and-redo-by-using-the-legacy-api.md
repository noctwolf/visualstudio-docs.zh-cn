---
title: 管理撤消和重做通过旧版 API |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a8a93b4fd12cd9a0bd2e5a5f3c70486e370545a9
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747646"
---
# <a name="manage-undo-and-redo-by-using-the-legacy-api"></a>管理撤消和重做通过使用传统的 API
编辑器必须支持撤消操作，可让用户反转其最新更改时它们修改代码。 大多数编辑器实现下[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]和.NET Framework 可以撤消支持自动提供的集成的开发环境 (IDE)。

## <a name="in-this-section"></a>本节内容
- [如何：实现撤消管理](../extensibility/how-to-implement-undo-management.md)提供恢复数据的编辑器具有一个或多个视图的功能。

- [如何：清除撤消堆栈](../extensibility/how-to-clear-the-undo-stack.md)说明如何清除撤消堆栈。

- [如何：使用链接的撤消管理](../extensibility/how-to-use-linked-undo-management.md)Incorporates 链接到您的编辑器的撤消管理。

## <a name="reference"></a>参考
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager> 提供支持多个视图的编辑器的撤消管理。
