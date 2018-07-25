---
title: 如何： 响应中实时调试器 |Microsoft Docs
ms.custom: ''
ms.date: 05/23/17
ms.technology: vs-ide-debug
ms.topic: troubleshooting
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: 14972d5f-69bc-479b-9529-03b8787b118f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fd3f565d8bb58ae290b0b569bb61d4cb57e8edaa
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2018
ms.locfileid: "39179770"
---
# <a name="how-to-respond-to-the-just-in-time-debugger"></a>如何： 响应中实时调试器

请参阅实时中时应执行的操作调试程序对话框的依赖于要执行操作：

#### <a name="if-you-want-to-fix-or-debug-the-error-visual-studio-users"></a>如果你想要解决或调试错误 （Visual Studio 用户）

- 您必须具有[安装 Visual Studio](http://visualstudio.microsoft.com)若要查看有关错误的详细的信息，并尝试对其进行调试。 有关详细信息，请参阅[使用实时调试器进行调试](../debugger/debug-using-the-just-in-time-debugger.md)。 如果您不能解决该错误并修复应用程序，请联系应用的所有者，以解决该错误。

#### <a name="if-you-want-to-prevent-the-just-in-time-debugger-dialog-box-from-appearing"></a>如果你想要防止出现实时调试器对话框

您可以采取措施来防止实时中使其不显示调试器对话框。 如果应用程序处理错误，可以正常运行应用程序。

1. （web 应用）如果想要运行 web 应用，可以禁用脚本调试。

    对于 Internet Explorer 或 Edge，禁用脚本调试在 Internet 选项对话框中。 可以访问这些设置，从**Control Panel** > **网络和 Internet** > **Internet 选项**(确切步骤取决于你Windows 和你的浏览器的版本）。

    ![JITInternetOptions](../debugger/media/jitinternetoptions.png "JITInternetOptions")

    然后重新打开在其中找到错误的网页。 如果更改此设置不能解决此问题，请联系以解决此问题的 web 应用程序所有者。

3. （visual Studio 用户）如果已安装的 Visual Studio （或如果你有它以前安装，并将其删除），[禁用在实时调试](../debugger/debug-using-the-just-in-time-debugger.md)并尝试再次运行该应用。

    > [!IMPORTANT]
    > 如果禁用中实时调试并且应用程序时遇到未经处理的异常 （错误），您将相反，看到标准错误对话框或应用程序会崩溃或挂起。 错误修复 （由你或应用的所有者） 之前，不会正常运行应用程序。

2. （ASP.NET 和 IIS）如果托管在 IIS 中的 ASP.NET Web 应用，则禁用服务器端调试。

    在 IIS 管理器中，右键单击服务器节点，然后选择**切换到功能视图**。 在 ASP.NET 部分中，选择 **.NET 编译**，并确保你选择**False**为 （步骤会有所不同，在较旧版本的 IIS） 的调试行为。

## <a name="see-also"></a>请参阅
 [调试器基础知识](../debugger/getting-started-with-the-debugger.md)
