---
title: "Help Content Manager 重写 | Microsoft Docs"
ms.custom: 
ms.date: 11/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-help-viewer
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95fe6396-276b-4ee5-b03d-faacec42765f
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 143bc6af5aa42eb480d5eff736633c2df6e68979
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="help-content-manager-overrides"></a>Help Content Manager 重写
可以更改 Visual Studio IDE 中的 Help Viewer 和帮助相关功能的默认行为。 可通过创建 [.pkgdef](https://blogs.msdn.microsoft.com/visualstudio/2009/12/18/whats-a-pkgdef-and-why/) 文件来设置各种注册表项值，从而指定某些选项。 其他选项则直接在注册表中设置。

## <a name="how-to-control-help-viewer-behavior-by-using-a-pkgdef-file"></a>如何使用 .pkgdef 文件控制 Help Viewer 行为

1. 创建 .pkgdef 文件，且文件第一行为 `[$RootKey$\Help]`。

2. 添加下表所述的任一或所有注册表项值，每个值占一行，例如 `“UseOnlineHelp”=dword:00000001`。

3. 将文件复制到 %ProgramFiles(x86)%\Microsoft Visual Studio\2017\\<版本\>\Common7\IDE\CommonExtensions。

4. 在开发人员命令提示中运行 `devenv /updateconfiguration`。

### <a name="registry-key-values"></a>注册表项值
|注册表项值|类型|数据|描述|  
|------------------|----|----|-----------|  
|NewContentAndUpdateService|string|\<服务终结点的 http URL\>|定义唯一的服务终结点|
|UseOnlineHelp|dword|`0` 指定本地帮助，`1` 指定联机帮助|定义联机或脱机帮助（默认）|
|OnlineBaseUrl|string|\<服务终结点的 http URL\>|定义唯一的 F1 终结点|
|OnlineHelpPreferenceDisabled|dword|`0` 启用或 `1` 禁用联机帮助首选项|禁用联机帮助首选项|
|DisableManageContent|dword|`0` 启用或 `1` 禁用 Help Viewer 中的“管理内容”选项卡|禁用“管理内容”选项卡|
|DisableFirstRunHelpSelection|dword|`0` 启用或 `1` 禁用在 Visual Studio 首次启动时配置的帮助功能|禁用首次启动 Visual Studio 时的内容安装|

### <a name="example-pkgdef-file-contents"></a>示例 .pkgdef 文件内容
```
[$RootKey$\Help]
“NewContentAndUpdateService”=”https://some.service.endpoint”
“UseOnlineHelp”=dword:00000001
“OnlineBaseUrl”=”https://some.service.endpoint”
“OnlineHelpPreferenceDisabled”=dword:00000000
“DisableManageContent”=dword:00000000
“DisableFirstRunHelpSelection”=dword:00000001
```

## <a name="using-registry-editor-to-change-help-viewer-behavior"></a>使用注册表编辑器更改 Help Viewer 行为
可通过在注册表编辑器中设置注册表项值，控制以下两种行为。  
  
|任务|注册表项|值|数据|  
|----------|-----|------|----|
|替代 BITS 作业优先级|HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node（64 位计算机上）\Microsoft\Help\v2.3|BITSPriority|**foreground**、**high**、**normal** 或 **low**|
|指向网络共享上的本地内容存储区|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Help\v2.3\Catalogs\VisualStudio15|LocationPath|“*ContentStoreNetworkShare*”|
  
## <a name="see-also"></a>请参阅
[帮助查看器管理员指南](../ide/help-viewer-administrator-guide.md)  
[Help Content Manager 的命令行参数](../ide/command-line-arguments-for-the-help-content-manager.md)  
[Microsoft Help Viewer](../ide/microsoft-help-viewer.md)  
[通过使用 .pkgdef 文件修改独立 shell](../extensibility/shell/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)