---
ms.technology: vs-ai-tools
ms.openlocfilehash: f11a66fd06a2b0b3b23d35c3153c5dd26fab282e
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29709821"
---
# <a name="view-recent-job-performance-and-details"></a>查看最近的作业性能和详细信息
提交作业后，可以查看作业列表，以查看作业状态和持续时间等。

1. 在“服务器资源管理器”中，展开特定计算上下文
1. 双击“作业”
1. 可看见提交到该计算上下文的作业列表。
1. 在列表中选择一个特定的作业以查看详细信息

![监视作业](media\job-details\monitor-jobs.png)

> 提交到 Linux VM 的作业历史记录存储在 VM 上的 /tmp 目录中。 因此，每次重启时都会清除作业历史记录。 要永久记录作业历史记录，请将 VM 配置为 Azure 机器学习中的计算上下文，然后将作业提交到 Azure 机器学习（选择 VM 作为计算上下文）