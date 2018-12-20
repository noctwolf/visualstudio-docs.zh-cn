---
title: 负载测试的日志文件大小
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, logging
ms.assetid: 417059bf-37ae-4e7a-b9b0-29bd71f1414f
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: eb77c9c037a46ad1195482abfddd102f50bcd1ae
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53067270"
---
# <a name="how-to-specify-the-maximum-size-for-the-log-file-for-load-tests"></a>如何：指定负载测试的最大日志文件大小

默认情况下，用于负载测试的日志文件的最大大小设置为 20 MB。 可通过编辑与控制器服务关联的配置文件来更改此值。

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="specify-the-maximum-log-file-size-for-load-test"></a>指定负载测试的最大日志文件大小

1.  打开位于 %ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTCcontroller.exe.config 中的 QTCcontroller.exe.config XML 配置文件。

2.  在 `<add key="LogSizeLimitInMegs" value="20"/>` 标记下找到 `<appSettings>` 项。

    ```xml
    <appSettings>
        <add key="LogSizeLimitInMegs" value="20"/>
        <add key="AgentConnectionTimeoutInSeconds" value="120"/>
        <add key="AgentSyncTimeoutInSeconds" value="300"/>
        <add key="ControllerServicePort" value="6901"/>
        <add key="ControllerUsersGroup" value="TeamTestControllerUsers"/>
        <add key="ControllerAdminsGroup" value="TeamTestControllerAdmins"/>
        <add key="CreateTraceListener" value="no"/>
      </appSettings>
    ```

3.  将 `value ="20"` 修改为要为日志文件指定的最大允许大小。

    > [!NOTE]
    > 如果输入值“0”，则指定日志文件大小仅受限于可用磁盘空间。

## <a name="see-also"></a>请参阅

- [修改负载测试记录设置](../test/modify-load-test-logging-settings.md)
- [为测试控制器和测试代理配置端口](../test/configure-ports-for-test-controllers-and-test-agents.md)