---
redirect_url: /visualstudio/ide/microsoft-help-viewer
ms.openlocfilehash: c0b1a114eb157860dd70873929727cc56f1d6514
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
title: "Help Viewer 疑难解答 | Microsoft Docs" ms.custom: "" ms.date: "11/04/2016" ms.reviewer: "" ms.suite: "" ms.technology: 
  - "vs-help-viewer" ms.tgt_pltfrm: "" ms.topic: "article" helpviewer_keywords: 
  - "疑难解答 [Help Viewer]"
  - "Help Viewer，疑难解答" ms.assetid: 461a4553-064a-4142-a2d2-058658b9ba12 caps.latest.revision: 13 author: "gewarren" ms.author: "gewarren" manager: ghogen
---
# <a name="troubleshooting-the-help-viewer"></a>帮助查看器疑难解答
本主题讨论使用 Help Viewer 时可能会遇到的问题。  
  
## <a name="audio-doesnt-work"></a>音频不起作用。  
 Help Viewer 不包含音频播放器。 如果下载的内容包含音频，但选择“播放”后没有任何反应，请安装音频播放器。  
  
## <a name="search-doesnt-work-in-windows-server-2008-windows-server-2008-with-sp1-or-windows-server-2008-r2"></a>Windows Server 2008、Windows Server 2008 SP1 或 Windows Server 2008 R2 中的搜索不起作用。  
 Help Viewer 中的搜索和筛选器功能需要安装并打开 Windows Search 服务。 默认情况下，Windows Server 2008、Windows Server 2008 Service Pack 1 (SP1) 和 Windows Server 2008 R2 中的此服务处于关闭状态。  
  
#### <a name="to-activate-windows-search-service"></a>激活 Windows Search 服务  
  
1.  启动服务器管理器。  
  
2.  在左侧导航窗格中，选择“角色”。  
  
3.  在“角色摘要”窗格中，选择“添加角色”。  
  
4.  选择“文件服务”角色，然后选择“下一步”按钮。  
  
5.  选择 Windows Search 角色服务。  
  
## <a name="additional-resources"></a>其他资源  
 通过使用以下资源，可以获取更多信息，并针对 Help Viewer 提供反馈：  
  
-   若要提供反馈，请参阅 Microsoft 网站上的 [Microsoft Connect](http://go.microsoft.com/fwlink/?linkid=243983) 或发送电子邮件到 [hlpfdbk@microsoft.com](mailto:hlpfdbk@microsoft.com)。  
  
-   有关详细信息，请浏览[开发人员文档和帮助系统](http://go.microsoft.com/fwlink/?LinkId=232741)论坛。  
  
## <a name="see-also"></a>请参阅
[帮助查看器管理员指南](http://go.microsoft.com/fwlink/?LinkId=243985)