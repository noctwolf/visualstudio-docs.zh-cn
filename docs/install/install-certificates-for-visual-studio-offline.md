---
title: 安装 Visual Studio 脱机安装所需的证书 | Microsoft Docs
description: 介绍安装 Visual Studio 脱机安装证书所需的步骤
ms.date: 08/30/2017
ms.reviewer: tims
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 9750A3F3-89C7-4A8F-BA75-B0B06BD772C2
author: tglee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 548e00743381e6a2c39d87d82c587b26f944702a
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="install-certificates-required-for-visual-studio-offline-installation"></a>安装 Visual Studio 脱机安装所需的证书

Visual Studio 主要供连接 Internet 的计算机上安装，因为许多组件需要定期更新。 不过，通过额外执行一些步骤，可以在未连接 Internet 的环境中部署 Visual Studio。

Visual Studio 安装程序引擎仅安装受信任的内容。 为此，它会检查正在下载内容的验证码签名，并在安装前验证所有内容是否受信任。 这样可以保证用户环境的安全，在下载位置受到威胁时免受攻击。 因此，Visual Studio 安装程序要求在用户的计算机上安装多个标准的 Microsoft 根证书和中间证书，并保持最新版本。 如果计算机通过 Windows 更新保持最新状态，则签名证书通常是最新状态。 如果计算机连接到 Internet，则在安装过程中，Visual Studio 可能会根据需要刷新证书以验证文件签名。 如果计算机处于脱机状态，则必须采用其他方式刷新证书。

## <a name="how-to-refresh-certificates-when-offline"></a>如何在处于脱机状态时刷新证书

有三个选项可用于在脱机环境中安装或更新证书。

### <a name="option-1---manually-install-certificates-from-a-layout-folder"></a>选项 1 - 从布局文件夹手动安装证书

创建网络布局时，所需证书会下载到 Certificates 文件夹。 然后可以双击每个证书文件，并单击完成证书管理器向导，从而手动安装证书。 如果看到输入密码提示，请将密码留空。

### <a name="option-2---distribute-trusted-root-certificates-in-an-enterprise-environment"></a>选项 2 - 在企业环境中分发受信任的根证书

对于企业，如果脱机计算机不具有最新的根证书，管理员可以按照[配置受信任根和不允许的证书](https://technet.microsoft.com/library/dn265983.aspx)页来更新证书。

### <a name="option-3---install-certificates-as-part-of-a-scripted-deployment-of-visual-studio"></a>选项 3 - 在 Visual Studio 的脚本化部署过程中安装证书

如果正在编写在脱机环境中将 Visual Studio 部署到客户端工作站的脚本，应执行以下步骤：

1. 将[证书管理器工具](/dotnet/framework/tools/certmgr-exe-certificate-manager-tool) (certmgr.exe) 复制到安装共享（例如，\\server\share\vs2017）。 Windows 自身不附带 Certmgr.exe，但 [Windows SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) 可以提供。

2. 使用下面的命令创建批处理文件：

   ```cmd
   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Code Signing PCA 2011" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Time-Stamp PCA 2010" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Code Signing PCA" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root
   ```

3. 将批处理文件部署到客户端。 应从提升的进程中运行此命令。

## <a name="what-are-the-certificates-files-in-the-certificates-folder"></a>Certificates 文件夹中的证书文件有哪些？

此文件夹有三个 .P12 文件，每个文件都包含中间证书和根证书。 采用 Windows 更新的大多数系统都已安装这些证书。

* **ManifestSignCertificates.p12** 包含：
    * 中间证书： Microsoft 代码签名 PCA 2011
        * 不要求。 如果存在，可以在某些情况下提高性能。
    * 根证书： Microsoft 根证书颁发机构 2011
        * 未安装最新的 Windows 更新的 Windows 7 Service Pack 1 系统需要此证书。
* **ManifestCounterSignCertificates.p12** 包含：
    * 中间证书： Microsoft 时间戳 PCA 2010
        * 不要求。 如果存在，可以在某些情况下提高性能。
    * 根证书： Microsoft 根证书颁发机构 2010
        * 未安装最新的 Windows 更新的 Windows 7 Service Pack 1 系统需要此证书。
* **Vs_installer_opc.SignCertificates.p12** 包含：
    * 中间证书： Microsoft 代码签名 PCA
        * 所有系统均需要此证书。 请注意，通过 Windows 更新实现所有更新的系统可能没有此证书。
    * 根证书： Microsoft 根证书颁发机构
        * 必须的。 运行 Windows 7 或更高版本的系统附带此证书。

## <a name="why-are-the-certificates-from-the-certificates-folder-not-installed-automatically"></a>为什么无法自动安装 Certificates 文件夹中的证书？

如果是在联机环境中验证签名，Windows API 可用于下载证书并将其添加到系统中。 在此过程中，可通过管理设置验证证书是否受信任且已获允许。 在大多数脱机环境中，无法执行此验证过程。 通过手动安装证书，企业管理员不仅能够确保使用受信任的证书，而且还能够符合组织的安全策略。

## <a name="checking-if-certificates-are-already-installed"></a>检查是否已安装证书

检查安装系统的一种方法是按以下步骤操作：
1. 运行 **mmc.exe**。<br/>
  a. 单击“文件”，然后选择“添加/删除管理单元”。<br/>
  b. 双击“证书”，选择“计算机帐户”，然后单击“下一步”。<br/>
  c. 选择“本地计算机”，依次单击“完成”和“确定”。<br/>
  d. 展开“证书(本地计算机)”。<br/>
  e. 展开“受信任的根证书颁发机构”，选择“证书”。<br/>
    * 检查此列表中是否有必需的根证书。<br/>

   f. 展开“中间证书颁发机构”，选择“证书”。<br/>
    * 检查此列表中是否有需要的中间证书。<br/>

2. 单击“文件”，然后选择“添加/删除管理单元”。<br/>
  a. 双击“证书”，选择“我的用户帐户”，单击“完成”和“确定”。<br/>
  b. 展开“证书 - 当前用户”。<br/>
  c. 展开“中间证书颁发机构”，选择“证书”。<br/>
    * 检查此列表中是否有需要的中间证书。<br/>

如果证书名称不在“颁发对象”列中，请安装这些证书。  如果中间证书仅在“当前用户”中间证书存储中，则仅供已登录的用户使用。 可能需要为其他用户安装它。

## <a name="install-visual-studio"></a>安装 Visual Studio

安装证书后，可以根据“创建 Visual Studio 网络安装”页中的[从网络安装部署](create-a-network-installation-of-visual-studio.md#deploying-from-a-network-installation)部分中的说明，继续部署 Visual Studio。

## <a name="get-support"></a>获取支持
有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：
* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题，并在其中提问和找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。  （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅
* [安装 Visual Studio](install-visual-studio.md)
* [Visual Studio 管理员指南](visual-studio-administrator-guide.md)
* [使用命令行参数安装 Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio 工作负荷和组件 ID](workload-and-component-ids.md)
