---
title: 文件跟踪 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- msbuild, file tracking
ms.assetid: e6c66ac0-3464-451f-9192-3b98dca21b4a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 878d4d7e56c51d8a41a0e3cf3e78d6c83ed5d0b5
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55027667"
---
# <a name="file-tracking"></a>文件跟踪
文件跟踪记录对某个进程及其子进程的 Windows 文件系统的调用。 通过调用下列函数，程序会控制打开和关闭此日志记录的时间，并指定要使用的日志文件。  
  
 [EndTrackingContext](../msbuild/endtrackingcontext.md)  
 停止跟踪当前上下文。  
  
 [ResumeTracking](../msbuild/resumetracking.md)  
 调用 [SuspendTracking](../msbuild/suspendtracking.md) 后继续跟踪。  
  
 [SetThreadCount](../msbuild/setthreadcount.md)  
 设置用于跟踪的线程数。  
  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)  
 开始新的跟踪上下文。  
  
 [StartTrackingContextWithRoot](../msbuild/starttrackingcontextwithroot.md)  
 使用指定的根开始新的跟踪上下文。  
  
 [StopTrackingAndCleanup](../msbuild/stoptrackingandcleanup.md)  
 结束跟踪并释放占用的资源。  
  
 [SuspendTracking](../msbuild/suspendtracking.md)  
 暂时暂停跟踪。  
  
 [WriteAllTLogs](../msbuild/writealltlogs.md)  
 写出所有上下文的跟踪日志。  
  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)  
 写出当前上下文的跟踪日志。