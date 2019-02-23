---
title: 如何：使用链接的撤消管理 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - linked undo management
ms.assetid: af5cc22a-c9cf-45b1-a894-1022d563f3ca
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6ab15f46aedf569e21b00b51df4014fa39e4eec5
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56702403"
---
# <a name="how-to-use-linked-undo-management"></a>如何：使用链接的撤消管理
链接的撤消允许用户同时撤消中多个文件相同的编辑。 例如，跨多个程序文件，如标头文件和 Visual c + + 文件，同时进行文本更改是链接的撤消事务。 链接的撤消功能内置的撤消管理器中，环境的实现和<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager>用于处理此功能。 链接的撤消由一个父撤消单元，可以链接在一起以被视为单个撤消单元的单独撤消堆栈实现。 使用链接的撤消过程将在下一节中详细介绍。

## <a name="to-use-linked-undo"></a>若要使用的链接的撤消

1.  调用`QueryService`上`SVsLinkedUndoManager`获取一个指向`IVsLinkedUndoTransactionManager`。

2.  通过调用创建的初始父链接的撤消单元<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.OpenLinkedUndo%2A>。 这将设置撤消堆栈，以组合的链接的撤消堆栈为一组的起始点。 在`OpenLinkedUndo`还需要指定是要链接的撤消严格或非严格的方法。 非严格的链接的撤消行为意味着一些具有链接的撤消同级的文档可以关闭，仍然保留的其他链接撤消其堆栈上的同级。 严格的链接的撤消行为指定所有链接的撤消同级堆栈，必须在一起或根本不能撤消。 添加后续链接通过调用撤消堆栈[IOleUndoManager::Add](/windows/desktop/api/ocidl/nf-ocidl-ioleundomanager-add)方法。

3.  调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.CloseLinkedUndo%2A>以便为所有作为一个链接的撤消单元。

    > [!NOTE]
    >  若要实现链接的撤消管理在编辑器中，添加撤消管理。 有关实现链接的撤消管理的详细信息，请参阅[如何：实现撤消管理](../extensibility/how-to-implement-undo-management.md)。

## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>
- [IOleParentUndoUnit](/windows/desktop/api/ocidl/nn-ocidl-ioleparentundounit)
- [IOleUndoUnit](/windows/desktop/api/ocidl/nn-ocidl-ioleundounit)
- [如何：实现撤消管理](../extensibility/how-to-implement-undo-management.md)