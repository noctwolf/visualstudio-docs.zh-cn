---
title: 签名 VSIX 包 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- signature
- signing
- authenticode
- vsix
- packages
ms.assetid: e34cfc2c-361c-44f8-9cfe-9f2be229d248
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 84166ed96fb49567f4ede3e8e0c4b7e8ba3cc814
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31142287"
---
# <a name="signing-vsix-packages"></a>签名 VSIX 包
扩展程序集不需要他们可以运行在 Visual Studio 中，但它是作为最佳做法，这样做之前进行签名。  
  
 如果你想要保护你的扩展，并确保它尚未被篡改，你可以向 VSIX 包中添加数字签名。 VSIX 进行了签名，VSIX 安装程序将显示一条消息，该值指示对其签名，以及有关签名本身的详细信息。 如果 VSIX 的内容进行了修改，并且不重新签名 VSIX，VSIX 安装程序将显示签名无效。 未停止安装，但将警告用户。  
  
> [!IMPORTANT]
>  从 2015年开始，使用 SHA256 加密以外的任何签名的 VSIX 包将标识为具有签名无效。 VSIX 安装不会被阻止，但将警告用户。  
  
## <a name="signing-a-vsix-with-vsixsigntool"></a>签名与 VSIXSignTool VSIX  
 没有签名工具，可从 SHA256 加密[VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility)在 nuget.org 上[VsixSignTool](http://www.nuget.org/packages/Microsoft.VSSDK.Vsixsigntool)。  
  
#### <a name="to-use-the-vsixsigntool"></a>若要使用 VSIXSignTool  
  
1.  将你的 VSIX 添加到项目。  
  
2.  右键单击解决方案资源管理器中的项目节点选择**添加&#124;管理 NuGet 包**。  有关 NuGet 和添加 NuGet 包，请参阅详细信息请参阅[NuGet 文档](/NuGet)和[包管理器 UI](/NuGet/Tools/Package-Manager-UI)主题。  
  
3.  从 VisualStudioExtensibility VSIXSignTool 搜索并安装 NuGet 包。  
  
4.  你现在可以从项目的本地包位置运行 VSIXSignTool。 请参考此工具的命令行帮助以你的签名方案 (VSIXSignTool.exe /？)。  
  
 有关密码受保护的证书文件进行签名的示例：  
  
 VSIXSignTool.exe 登录 /f \<certfile >/p\<密码 > \<VSIXfile >  
  
## <a name="see-also"></a>另请参阅  
 [传送 Visual Studio 扩展](../extensibility/shipping-visual-studio-extensions.md)