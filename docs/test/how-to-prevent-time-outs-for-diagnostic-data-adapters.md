---
title: Visual Studio 中诊断数据适配器的超时
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, increasing time-outs
ms.assetid: 39fff4fc-9233-4f67-96ac-e81bbaf7ca82
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 8359aa76dc2f62afb63f6a36984492210d9aeeff
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2018
ms.locfileid: "39380009"
---
# <a name="how-to-prevent-time-outs-for-diagnostic-data-adapters"></a>如何：防止诊断数据适配器超时

如果在测试设置中使用诊断数据适配器，则启动测试运行时，会因以下某种原因发生超时：

-   测试控制器服务未在测试控制器计算机上运行。 可能必须重新启动服务。 有关如何确定测试控制器和管理测试控制器的详细信息，请参阅[通过 Visual Studio 管理测试控制器和测试代理](../test/manage-test-controllers-and-test-agents.md)。

-   如果在远程计算机上收集数据，则防火墙可能会阻止 Microsoft 测试管理器。 运行 Microsoft 测试管理器的计算机必须接受从测试控制器传入的连接。 当 Microsoft 测试管理器因防火墙阻止而未接收来自控制器的消息时，会发生超时。 必须检查运行 Microsoft 测试管理器的计算机上的防火墙设置。

-   测试控制器不能解析运行 Microsoft 测试管理器的计算机的名称。 如果 DNS 提供的此计算机的地址错误，则可能发生这种情况。 您可能必须与网络管理员联系才能解决此问题。

当你运行必须收集大量数据的长时间测试时，可能会发现收集此类数据超时。可使用下面的过程来解决此问题。

可以增大超时，方法是更新 Microsoft 测试管理器的配置文件，或更新发生超时的测试代理的配置文件。

Microsoft 测试管理器的配置文件名称为 mtm.exe.config。该文件位于以下目录中：%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE。

若要更新测试代理，必须更新测试代理计算机上的以下配置文件。 所有这些文件都位于测试代理计算机上的相同目录中：%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE。

-   QTAgent.exe.config

-   QTAgent32.exe.config

-   QTDCAgent.exe.config

-   QTDCAgent32.exe.config

如果你运行手动测试并收集环境中的数据，则在创建 Bug 时或测试用例完成时，诊断数据适配器已经收集的任何数据都将传输到正在运行手动测试的计算机。 如果您已收集大量数据或者您的网络连接缓慢，则花费的时间可能会长于 60 秒的默认值。 例如，如果已将 IntelliTrace 适配器配置为收集 IntelliTrace 事件并调用许多进程的信息，则此类数据传输时间可能会超过默认超时。若要增加此值，可使用以下过程更新 mtm.exe.config。

如果测试运行程序活动超时，或者某个测试代理超时，则会显示错误消息。测试代理的错误消息包含有关超时的测试代理计算机的信息。使用下面的过程可根据接收到的错误消息，来更新配置文件。

## <a name="to-increase-the-time-outs-for-your-diagnostic-data-adapters"></a>增大诊断数据适配器的超时

1.  打开“Windows 资源管理器”（或“文件资源管理器”）窗口。

     为此，请右击“开始”，并指向“资源管理器”。

    > [!NOTE]
    > 可能需要管理特权才能更新文件。

2.  在计算机上找到目录 %ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE，该目录包含必须更新的文件。

3.  右击该文件，然后指向“打开方式”。 选择一个编辑器。

     文件会在该编辑器中显示。 此文件中存储了很多设置。 其中的大多数设置都可使用 Microsoft 测试管理器进行更改。 但是，必须按照以下步骤所述，手动更改超时设置。

4.  必须修改测试执行设置部分以增大超时值。 此部分具有以下格式：

    ```text
    <!-- Begin: Test execution settings -->

        <!-- How long test runner will wait for an event raised to all local data collectors to complete.  Default is 300. -->
        <add key="DataCollectorEventTimeoutInSeconds" value="300"/>

        <!-- How long test runner will wait for test run operations, such as starting or stopping a test run, to complete.  Default is 60. -->
        <add key="RunOperationTimeoutInSeconds" value="60"/>

        <!-- End: Test execution settings -->
    ```

5.  要增加诊断数据适配器等待事件完成的时间，请增大 DataCollectorEventTimeoutInSeconds 键的值。

6.  如果超时错误消息是针对测试运行程序活动，则必须增大键 RunOperationTimeoutInSeconds 的值。

7.  若要增加传输针对 Bug 收集的任何数据的超时或运行测试的计算机上测试结束时的超时，必须将以下超时添加到文件的 appSettings 部分的 mtm.exe.config 中：

    ```text
    <!-- How long test runner waits for data collected by diagnostic data adapters to be transferred to the computer. Default is 60 seconds. -->
    <add key="GetCollectorDataTimeout" value="300"/>
    ```

    > [!NOTE]
    > 超时值以秒为单位。

8.  保存对文件所做的更改，然后重新运行以前超时的测试。

## <a name="see-also"></a>请参阅

- [使用测试设置收集诊断信息](../test/collect-diagnostic-information-using-test-settings.md)