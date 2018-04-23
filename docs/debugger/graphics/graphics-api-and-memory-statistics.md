---
title: 图形 API 和内存统计信息 |Microsoft 文档
ms.custom: ''
ms.date: 03/02/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.apistatistics
- vs.graphics.memorystatistics
ms.assetid: 27d2f303-e3ed-4219-9009-345a0d849506
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 48c8ed3c8c2ebffc57ac46e987dbc37950cba0fd
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="graphics-api-and-memory-statistics"></a>图形 API 和内存统计信息
<!-- VERSIONLESS -->
Visual Studio 2017 和更好的支持图形 API 统计信息和内存统计信息工具。  这两种工具，可以查看有关 Direct3D API 使用情况，以及 GPU 内存消耗的各种资源的信息的各种位。

## <a name="graphics-api-statistics"></a>图形 API 统计信息
Visual Studio 图形诊断中的图形 API 统计信息，可以查看所有所做的 Direct3D 调用和每个调用的计数。  若要查看窗口，请选择**视图 > API 统计信息**菜单项。

![API 统计信息](media/gfx_diag_api_statistics.png)

此工具可以非常方便在发现你可能没有意识到你的 DirectX 调用正在进行，或要过于频繁进行的调用中。

您可以右键单击在窗口中复制所有数据以 CSV，可以进行进一步分析粘贴到 Excel 类似的形式。

## <a name="memory-statistics"></a>内存统计信息
此工具将显示在框架中创建图形驱动程序分配的资源的内存量。  若要查看此窗口，请选择**视图 > 内存统计信息**菜单项。

![内存统计信息](media/gfx_diag_memory_statistics.png)

**GPU 分配**列显示的事件中显示所用的内存量**事件**列。  你还可以选择监视图标![监视图标](media/gfx_watch.png)查看[资源历史记录](graphics-event-list.md#resource-history)所选事件。

与 API 统计信息工具中，你可以为 CSV，可以进行进一步分析粘贴到 Excel 类似右键单击在窗口中复制所有数据。

## <a name="see-also"></a>请参阅  
[图形诊断 （调试 DirectX 图形）](visual-studio-graphics-diagnostics.md)   
[资源历史记录](graphics-event-list.md#resource-history)
<!-- /VERSIONLESS -->