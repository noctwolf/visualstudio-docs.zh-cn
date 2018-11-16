---
title: 预提取 Windows 应用商店应用程序的内容 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: b4481fef-3ebf-4f7d-9748-d43821a0ebac
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7ad7c09e163833c295be45a7ee81e2e0587fa6b2
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51797398"
---
# <a name="prefetch-content-for-windows-store-apps"></a>预提取 Windows 应用商店应用的内容
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

仅适用于 Windows] (../Image/windows_only_content.png"windows_only_content")  
  
 若要使 Windows 应用商店应用的响应速度更快，可以请求 Windows 将预一些 web 内容，如网页或图像加载到应用程序的[WinINet](http://msdn.microsoft.com/en-us/0a06f2af-957a-4dff-a8cc-187370181b5c)[WinINet](http://msdn.microsoft.com/library/aa383630.aspx)缓存。 此功能称为“预提取”。 它对于启动时使用的内容特别有效，但你也可以预提取其他常用内容。 方法[Windows.Networking.BackgroundTransfer.ContentPrefetcher](http://msdn.microsoft.com/library/windows/apps/windows.networking.backgroundtransfer.contentprefetcher.aspx)类允许您指定你想要预加载内容的 Uri。 请参阅 Windows SDK[内容预提取示例](http://code.msdn.microsoft.com/windowsapps/ContentPrefetcher-Sample-432c8309)有关如何将 ContentPrefetcher 功能添加到您的应用程序的示例。  
  
 Windows 使用试探法来确定何时及是否应进行预提取，以及将下载哪些资源。 试探法将考虑系统网络和电源情况、用户应用使用情况历史记录和之前预提取尝试的结果。 在 Visual Studio 中，你可以使用**触发 Windows 应用商店应用预提取**命令强制 Windows 忽略 ContentPrefetcher 试探法并预加载所有指定的 web 内容。 若要在已知状态（已加载或未加载）下使用要预提取的内容测试应用程序的行为或性能，这会很有用。  
  
## <a name="to-force-preloading-of-contentprefetcher-specified-resources"></a>强制预加载 ContentPrefetcher 指定的资源  
 此过程假定你已在应用程序项目中设置 ContentPrefetcher 功能并指定预加载的内容 URI。 若要在指定资源为新的或已修改时强制预加载内容，您需要启动和停止应用程序，在选择之前**触发 Windows 应用商店应用预提取**命令。 先运行应用程序以注册 URI。 **触发 Windows 应用商店应用预提取**命令然后将强制 ContentPrefetcher 下载此内容并将其添加到缓存。 在应用程序的后续运行中，你可以假定已预加载此内容。  
  
1. 启动应用程序以将预提取内容 URI 注册到应用程序。 上**调试**菜单中，选择**开始调试**(键盘快捷键： F5)。  
  
2. 上**调试**菜单中，选择**停止调试**(键盘快捷键： Shift + F5)。  
  
3. 上**调试**菜单中，选择**其他调试目标**，然后选择**触发 Windows 应用商店应用预提取**。  
  
   现在可以利用预提取的 Web 资源来调试、测试或分析应用程序。  
  
> [!NOTE]
>  当你添加或修改指定的 Web 内容时，请重复上述步骤。  
  
## <a name="see-also"></a>请参阅  
 [博客文章： 触发预提取适用于 Windows 应用商店应用的 Visual Studio 2013 Update 2 中](http://blogs.msdn.com/b/visualstudioalm/archive/2014/02/06/triggering-prefetch-for-windows-store-apps-in-visual-studio-2013-update-2.aspx)



