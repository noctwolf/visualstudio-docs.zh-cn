---
title: 快照调试的常见问题解答 | Microsoft Docs
ms.date: 11/07/2017
ms.topic: reference
helpviewer_keywords:
- debugger
ms.assetid: 944f1eb0-a74b-4d28-ae2b-a370cd869add
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7ea593ad5f88ba29f6b1c0d7c64a129b8f71c7f5
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58857069"
---
# <a name="frequently-asked-questions-for-snapshot-debugging-in-visual-studio"></a>在 Visual Studio 中进行快照调试的常见问答解答

下面列出了在使用 Snapshot Debugger 调试实时 Azure 应用程序时可能出现的问题。

#### <a name="what-is-the-performance-cost-of-taking-a-snapshot"></a>获取快照的性能成本是什么？

当 Snapshot Debugger 捕获应用快照时，它会创建应用进程的分支并挂起分支的副本。 调试快照时，将针对进程的分支副本进行调试。 此过程只需 10-20 毫秒，但不会复制应用的完整堆。 而是仅复制页表并将页设置为写入时复制。 如果堆上的某些应用对象发生更改，则会复制其相应页。 这就是每个快照具有较小的内存中成本的原因（对于大多数应用，大约具有数百千字节）。

#### <a name="what-happens-if-i-have-a-scaled-out-azure-app-service-multiple-instances-of-my-app"></a>如果我有一个横向扩展的 Azure 应用服务（多个应用实例），会发生什么情况？

具有多个应用实例时，快照点会应用于每个实例。 只有符合指定条件的第一个快照点才会创建快照。 如果你有多个快照点，则后续快照将来自创建了第一个快照的同一个实例。 发送到输出窗口的记录点将仅显示来自一个实例的消息，而发送到应用程序日志的记录点将发送来自所有实例的消息。

#### <a name="how-does-the-snapshot-debugger-load-symbols"></a>Snapshot Debugger 如何加载符号？

若要使用 Snapshot Debugger，本地应用程序或部署到 Azure 应用服务的应用程序必须具有匹配的符号。 （目前不支持嵌入的 PDB。）Snapshot Debugger 将自动从 Azure 应用服务下载符号。 自 Visual Studio 2017 版本 15.2 起，部署到 Azure 应用服务时，也会同时部署应用的符号。

#### <a name="does-the-snapshot-debugger-work-against-release-builds-of-my-application"></a>Snapshot Debugger 是否适用于我的应用程序的发布版本？

是 - Snapshot Debugger 适用于发布版本。 当快照点置于某个函数中时，该函数被重新编译回调试版本，使其可调试。 停止 Snapshot Debugger 会将函数返回到发布版本的版本。

#### <a name="can-logpoints-cause-side-effects-in-my-production-application"></a>记录点是否可能在我的生产应用程序中产生副作用？

否 - 添加到应用的任何日志消息都会进行虚拟评估。 它们不会对你的应用程序产生任何副作用。 但是，可能无法使用记录点访问某些本机属性。

#### <a name="does-the-snapshot-debugger-work-if-my-server-is-under-load"></a>如果我的服务器处于负载中，Snapshot Debugger 是否会运行？

是，快照调试可用于处于负载中的服务器。 当服务器上的可用内存量较少时，Snapshot Debugger 会进行限制，并且不会捕获快照。

#### <a name="how-do-i-uninstall-the-snapshot-debugger"></a>如何卸载快照调试器？

可以通过执行以下步骤来卸载应用服务上的 Snapshot Debugger 站点扩展：

1. 通过 Visual Studio 中的 Cloud Explorer 或 Azure 门户禁用应用服务。
1. 导航到应用服务的 Kudu 站点（即，yourappservice.scm.azurewebsites.net）并导航到“站点扩展”。
1. 单击 Snapshot Debugger 站点扩展上的 X 以将其删除。

#### <a name="why-are-ports-opened-during-a-snapshot-debugger-session"></a>为什么在 Snapshot Debugger 会话期间打开端口？

Snapshot Debugger 必须打开一组端口才能调试在 Azure 中获取的快照，这些端口与远程调试所需的端口相同。 [可以在此处找到端口列表](../debugger/remote-debugger-port-assignments.md)。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中进行调试](../debugger/index.md)
- [使用快照调试器调试实时 ASP.NET 应用](../debugger/debug-live-azure-applications.md)
- [调试实时 ASP.NET Azure 虚拟 Machines\Virtual 机规模集使用快照调试程序](../debugger/debug-live-azure-virtual-machines.md)
- [调试实时 ASP.NET Azure Kubernetes，使用快照调试程序](../debugger/debug-live-azure-kubernetes.md)
- [快照调试疑难解答和已知问题](../debugger/debug-live-azure-apps-troubleshooting.md)