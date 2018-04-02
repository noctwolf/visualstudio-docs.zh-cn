---
title: Visual Studio 中的负载测试记录设置 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, logging, modifying
ms.assetid: 9649226a-857d-41ef-8ec7-047b6e498033
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: bc2916c6b5f109b3846095769468d8ddb55e7a09
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="modify-load-test-logging-settings"></a>修改负载测试记录设置

已完成的负载测试的负载测试结果包含从受测计算机的日志中定期收集的性能计数器样本和错误信息。 可以在负载测试运行过程中收集大量性能计数器样本。 所收集到的性能数据量取决于运行的长度、采样间隔、受测计算机的数量以及要收集的计数器的数量。 对于大型负载测试，所收集的性能数据量很容易就能达到数千兆字节；因此，你可能需要考虑修改将数据保存到日志的频率。 请参阅[测试控制器和测试代理](configure-test-agents-and-controllers-for-load-tests.md)。

测试控制器会在测试运行期间将收集的所有负载测试样本数据后台处理到一个数据库日志中。 其他数据（如计时详细信息和错误详细信息）会在测试完成时加载到该数据库中。

|任务|关联主题|
|----------|-----------------------|
|**指定负载测试运行期间保存日志的频率：**可以指定在负载测试运行时希望保存测试日志的频率。|-   [如何：指定保存测试日志的频率](../test/how-to-specify-how-frequently-test-logs-are-saved.md)|
|**在负载测试未通过时保存日志：**可以指定是否每当负载测试未通过就保存测试日志。|-   [如何：指定是否将测试失败保存到测试日志中](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)|
|**为日志文件设置最大文件大小：**可以编辑与测试控制器服务关联的 XML 配置文件，以指定要用于日志文件的最大文件大小。|[如何：为日志文件指定最大大小](../test/how-to-specify-the-maximum-size-for-the-log-file.md)|

## <a name="related-tasks"></a>相关任务

相关属性是“计时详细信息存储”。 有关详细信息，请参阅[如何：配置收集完整详细信息以启用虚拟用户活动图表](../test/how-to-configure-load-tests-to-collect-full-details.md)。

## <a name="see-also"></a>请参阅

- [配置负载测试运行设置](../test/configure-load-test-run-settings.md)