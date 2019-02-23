---
title: 管理撤消和重做通过旧版 API |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: adf6a2405ae3d3408f9cf04199ba05dff9232326
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56687791"
---
# <a name="manage-undo-and-redo-by-using-the-legacy-api"></a>管理撤消和重做通过使用传统的 API
编辑器必须支持撤消操作，可让用户反转其最新更改时它们修改代码。 在实现大多数编辑器[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]和[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]可以撤消支持自动提供的集成的开发环境 (IDE)。

## <a name="in-this-section"></a>本节内容
- [如何：实现撤消管理](../extensibility/how-to-implement-undo-management.md)提供恢复数据的编辑器具有一个或多个视图的功能。

- [如何：清除撤消堆栈](../extensibility/how-to-clear-the-undo-stack.md)说明如何清除撤消堆栈。

- [如何：使用链接的撤消管理](../extensibility/how-to-use-linked-undo-management.md)Incorporates 链接到您的编辑器的撤消管理。

## <a name="reference"></a>参考
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager> 提供支持多个视图的编辑器的撤消管理。
