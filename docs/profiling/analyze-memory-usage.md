---
title: 分析内存使用情况
ms.custom: seodec18
ms.date: 01/02/2018
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4f06685be91926e4168c5e4592514469f94da47d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54932605"
---
# <a name="analyze-memory-usage"></a>分析内存使用情况
使用集成了调试器的内存使用率诊断工具，查找内存泄漏和低效内存使用的情况。 通过内存使用率工具可以拍摄托管和本机内存堆的一个或多个快照  。 可收集 .NET、ASP.NET、本机或混合模式（.NET 和本机）应用的快照。  
  
-   你可以分析单个快照以了解有关内存使用的对象类型的相对影响，并在你的应用中查找低效使用内存的代码。  
  
-   你还可以比较 (diff) 一个应用的两个快照，以便在你的代码中查找导致内存使用随时间增加的区域。  

有关详细说明，请参阅[分析内存使用率](../profiling/memory-usage.md)教程。  目前，必须使用随附调试器的工具，才能度量 .NET Core 应用的内存使用情况。 对于其他托管应用和本机应用，可使用随附或未随附调试器的工具。

可 Windows 7 及更高版本中使用不带调试器的分析工具。 要运行带调试器的分析工具（“诊断工具”窗口），需具备 Windows 8 及更高版本。
  
## <a name="blogs-and-videos"></a>博客和视频  

| | |
|---------|---------|
| ![视频的摄像机图标](../install/media/video-icon.png "观看视频") | [观看介绍诊断工具用法的视频](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Profiling-with-Diagnostics-Tools-in-Visual-Studio-2017-daHnzMD6D_9211787171)，了解如何在 Visual Studio 2017 中分析内存使用率以及 CPU 使用率。 |

 [调试时分析 CPU 和内存](https://blogs.msdn.microsoft.com/visualstudio/2016/02/15/analyze-cpu-memory-while-debugging/)  
  
 [Visual C++ 博客：Visual C++ 2015 中的内存分析](https://blogs.msdn.microsoft.com/vcblog/2015/10/21/memory-profiling-in-visual-c-2015/)  

## <a name="see-also"></a>请参阅
 [使用 Visual Studio 分析](../profiling/index.md)  
 [首先了解分析工具](../profiling/profiling-feature-tour.md)