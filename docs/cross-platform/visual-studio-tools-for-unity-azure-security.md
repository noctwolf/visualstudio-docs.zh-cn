---
title: "Visual Studio Tools for Unity Azure 演练安全 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: F4FD6E1C-EA64-4613-BDDE-6E4E5CCF983E
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 1ffb0c57329a8453208978cee69daa771d8ee0e9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="update-unity-mono-security-certificate-store"></a>更新 Unity Mono 安全证书存储

Unity 的 Mono 附带一个空证书存储，因此不信任任何站点。 有关详细信息，可参阅 [Mono security FAQ](http://www.mono-project.com/docs/faq/security/)（Mono 安全性常见问题解答）。

若要连接到 Azure 且不忽略 TLS/SSL，必须更新 Unity Mono 证书存储。

## <a name="using-mozroots-to-install-certificates"></a>使用 mozroots 安装证书

Mono 包含 mozroots 工具。 该工具用于下载和安装 Mozilla 的根证书列表。

1. 打开命令提示符终端。

2. 在终端中导航到 **C:\Program Files\Unity\Editor\Data\MonoBleedingEdge\bin>** 目录。 确切位置可能不同，具体取决于在本地计算机上安装 Unity 的位置。

3. 键入以下命令，然后按 **Enter** 运行该命令：

  `mono ..\lib\mono\4.5\mozroots.exe --sync --import`

4. 应该会获得以下输出（虽然添加的证书数目可能不同）：

  ```
  Downloading from 'https://hg.mozilla.org/releases/mozilla-release/raw-file/default/security/nss/lib/ckfw/builtins/certdata.txt'...
  Importing certificates into user store...
  1 new root certificates were added to your trust store.
  Import process completed.
  ```

5. 现在应该能够运行示例项目，而且不会收到 TLS 相关错误。

## <a name="next-step"></a>下一步

* [测试客户端连接](visual-studio-tools-for-unity-azure-connection.md)
