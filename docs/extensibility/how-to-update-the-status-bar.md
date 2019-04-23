---
title: 如何：更新状态栏 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - update status bar
ms.assetid: 7500c8a7-4913-4818-a88b-bfd1b9887cb6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 88acd6cf55e8d03b355f1defb861bc5ae919ed52
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60047964"
---
# <a name="how-to-update-the-status-bar"></a>如何：更新状态栏
**状态栏**控件条位于底部的多个应用程序窗口，其中包含一个或多个状态文本行或指示器。

## <a name="to-update-the-status-bar"></a>若要更新状态栏

1. 实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>提供你的编辑器，例如，窗体视图和代码视图的每个单独的视图对象 (DocView)。

2. 当调用 IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>，更新中的信息**状态栏**通过调用的方法<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>。

    > [!NOTE]
    >  IDE 调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>仅当文档窗口最初已激活。 文档窗口处于活动状态的时间的其余部分中，必须更新**状态栏**编辑器更改的状态信息。

## <a name="robust-programming"></a>可靠编程
 一个**状态栏**包含四个单独的字段：

- 状态文本

- 进度栏

- 动画的图标

- 编辑器的信息

  有关详细信息，请参阅[状态栏](/cpp/mfc/status-bars)。

  IDE 将自动调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>方法在<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>文档窗口被激活时实现。

  VSPackage 实现器负责更新状态栏中的状态文本。 IDE 重置此字符串为"就绪"，如果 status 文本字段设置为空文本 ("") 在空闲时间。

## <a name="see-also"></a>请参阅
- [状态栏](/cpp/mfc/status-bars)