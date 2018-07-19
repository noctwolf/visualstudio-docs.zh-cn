---
title: 衡量 Python 代码的性能
description: 在使用基于 CPython 的解释器时，如何使用 Visual Studio 探查器来检查 Pyhon 代码的性能。
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 971eb7ce863fc4281d73e2d4d363805de22810f4
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37058625"
---
# <a name="profiling-python-code"></a>分析 Python 代码

可在使用基于 CPython 的解释器时分析 Python 应用程序。 （若要了解此功能可用于哪些 Visual Studio 版本，请参阅[功能矩阵 - 分析](overview-of-python-tools-for-visual-studio.md#matrix-profiling)。）

通过“分析”>“启动 Python 分析”菜单命令（这将打开配置对话框）开始分析：

![分析配置对话框](media/profiling-start.png)

选择“确定”后，探查器将运行并打开性能报告，通过此报告可以了解在应用程序中所用的时间：

![分析性能报告](media/profiling-results.png)

|   |   |
|---|---|
| ![视频的摄像机图标](../install/media/video-icon.png "观看视频") | 有关 Python 分析的演示，请[观看视频（Microsoft 虚拟学院）](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Profiling-Python-s6FoC6LWE_1005918567)（3 分 00 秒）。|

> [!Note]
> 目前，Visual Studio 仅支持此级别的全应用程序分析，但是我们当然希望听到你关于未来功能的反馈。 使用此页底部的[**提供产品反馈**按钮](#feedback)。

## <a name="profiling-for-ironpython"></a>IronPython 的分析

由于 IronPython 不是基于 CPython 的解释器，因此上述分析功能不会正常运行。

请通过直接启动 `ipy.exe` 作为目标应用程序并使用适当的参数来启动你的启动脚本，从而改用 Visual Studio.NET 探查器。 在命令行上包含 `-X:Debug`，以确保所有 Python 代码可进行调试和分析。 此参数会生成一个性能报告，其中包括在 IronPython 运行时和代码中所用的时间。 代码使用重整名称进行标识。

另外，IronPython 本身内置某些分析功能，但目前没有适合的可视化工具。 请参阅 [IronPython 探查器](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx)（MSDN 博客）查看可用内容。