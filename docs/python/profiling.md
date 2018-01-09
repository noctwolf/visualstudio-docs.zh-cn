---
title: "衡量 Visual Studio 中 Python 代码的性能 | Microsoft Docs"
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: python
ms.openlocfilehash: 525ff73c70b092ca97a9c53759ffa93d55d12c88
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="profiling-python-code"></a>分析 Python 代码

使用基于 CPython 的解释器时，Visual Studio 支持分析 Python 应用程序。

通过“分析”>“启动 Python 分析”菜单命令（这将打开配置对话框）开始分析：

![分析配置对话框](media/profiling-start.png)

选择“确定”后，探查器将运行并打开性能报告，通过此报告可以了解在应用程序中所用的时间：

![分析性能报告](media/profiling-results.png)

有关演示，请观看视频[分析 Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=hb46k6LWE_405918567)（Microsoft Virtual Academy，3 分 00 秒）。

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Testing-Python-hb46k6LWE_405918567]


## <a name="profiling-for-ironpython"></a>IronPython 的分析

由于 IronPython 不是基于 CPython 的解释器，因此上述分析功能不会正常运行。

请通过直接启动 `ipy.exe` 作为目标应用程序并使用适当的参数来启动你的启动脚本，从而改用 Visual Studio.NET 探查器。 在命令行上包含 `-X:Debug`，强制所有 Python 代码可进行调试和分析。 此参数会生成一个性能报告，其中包括在 IronPython 运行时和代码中所用的时间。 代码使用重整名称进行标识。

另外，IronPython 本身内置某些分析功能，但目前没有适合的可视化工具。 请参阅 [IronPython 探查器](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx)（MSDN 博客）查看可用内容。