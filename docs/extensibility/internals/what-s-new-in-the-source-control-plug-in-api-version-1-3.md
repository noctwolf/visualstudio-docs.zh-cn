---
title: 什么&#39;源中的新增功能的 s 控制插件的 API 版本 1.3 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, what's new in API v1.3
- what's new [Visual Studio SDK], source control plug-ins
ms.assetid: 7dfb2227-6e1d-4028-bce9-f8967456a993
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: abeb2a0a936a5d706e2e3744e9dd0f4e3123bdbf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="what39s-new-in-the-source-control-plug-in-api-version-13"></a>什么&#39;源中的新增功能的 s 控制插件的 API 版本 1.3
源控件插件 API 1.3 版引入了以下新功能，可提供更高级的控制。  
  
## <a name="changes"></a>更改  
 以下函数是对源控件插件 API 版本 1.3 全新的：  
  
|函数|概述|  
|--------------|--------------|  
|[SccGetExtendedCapabilities](../../extensibility/sccgetextendedcapabilities-function.md)|允许其他功能 bits 报告|  
|[SccEnumChangedFiles](../../extensibility/sccenumchangedfiles-function.md)|允许的版本控制的数据库比在本地磁盘中有较新版本的文件的检查|  
|[SccQueryChanges](../../extensibility/sccquerychanges-function.md)|允许在指定的文件的名称更改 （重命名、 添加和删除） 的状态的检查|  
|[SccPopulateDirList](../../extensibility/sccpopulatedirlist-function.md)|允许在版本控制数据库中进行检查的目录和文件|  
|[SccAddFilesFromSCC](../../extensibility/sccaddfilesfromscc-function.md)|将指定的文件列表从版本控制数据库添加到当前项目|  
|[SccBackgroundGet](../../extensibility/sccbackgroundget-function.md)|执行无提示"获取"的指定的文件 （显示为没有用户界面）|  
|[SccGetUserOption](../../extensibility/sccgetuseroption-function.md)|允许访问特定于用户的选项|  
  
## <a name="see-also"></a>另请参阅  
 [入门](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)   
 [源代码管理插件 API 版本 1.2 中的新增功能](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)