---
title: 在部署 Visual Studio 时自动应用产品密钥 | Microsoft Docs
ms.custom: ''
ms.date: 08/14/2017
ms.reviewer: tims
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1e9bfd9f72162d354d7e606d65146f602393d286
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="automatically-apply-product-keys-when-deploying-visual-studio"></a>在部署 Visual Studio 时自动应用产品密钥
可采用编程方式将产品密钥作为用于自动化 Visual Studio 部署的脚本的一部分进行应用。 安装 Visual Studio 期间或安装已完成后，可采用编程方式在设备上设置产品密钥。

## <a name="apply-the-license-after-installation"></a>安装完成后应用许可证
 可在静默模式下在目标计算机上使用 `StorePID.exe` 实用工具，从而使用产品密钥激活 Visual Studio 的已安装版本。 `StorePID.exe` 是在以下默认位置随 Visual Studio 2017 一起安装的实用工具程序： <br> `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE`

 通过使用 System Center 代理或提升的命令提示符，运行具有提升的权限的 `StorePID.exe`。 后接产品密钥和 Microsoft Product Code (MPC)。

>[!IMPORTANT]
> 请务必在产品密钥中添加短划线。

 ```
 StorePID.exe [product key including the dashes] [MPC]
 ```

 下面展示了用于应用 Visual Studio 2017 Enterprise 许可证（其中 MPC 为 08860，产品密钥为 `AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE`）的示例命令行（假设在默认安装位置上）：

 ```cmd
 "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\StorePID.exe" AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 08860
 ```

 下表列出了 Visual Studio 的每个版本的 MPC 代码：

| Visual Studio 版本                | MPC   |
|--------------------------------------|-------|
| Visual Studio Enterprise 2017        | 08860 |
| Visual Studio Professional 2017      | 08862 |
| Visual Studio Test Professional 2017 | 08866 |

如果 `StorePID.exe` 成功应用产品密钥，则会返回值为 0 的 `%ERRORLEVEL%`。 如果遇到错误，则会返回下列代码之一（具体视错误条件而定）：

| Error                     | 代码 |
|---------------------------|------|
| `PID_ACTION_SUCCESS`      | 0    |
| `PID_ACTION_NOTINSTALLED` | 1    |
| `PID_ACTION_INVALID`      | 2    |
| `PID_ACTION_EXPIRED`      | 3    |
| `PID_ACTION_INUSE`        | 4    |
| `PID_ACTION_FAILURE`      | 5    |
| `PID_ACTION_NOUPGRADE`    | 6    |

## <a name="get-support"></a>获取支持
有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：
* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题，并在其中提问和找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。  （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅
 * [安装 Visual Studio](../install/install-visual-studio.md)
 * [创建 Visual Studio 的脱机安装](../install/create-an-offline-installation-of-visual-studio.md)
