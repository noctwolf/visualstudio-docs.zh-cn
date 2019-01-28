---
title: 什么&#39;中的源控制插件 API 版本 1.3 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, what's new in API v1.3
- what's new [Visual Studio SDK], source control plug-ins
ms.assetid: 7dfb2227-6e1d-4028-bce9-f8967456a993
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6bb30e8a69885f4ad9f94372a2e93619790bd8a0
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54955240"
---
# <a name="what39s-new-in-the-source-control-plug-in-api-version-13"></a>什么&#39;中的源控制插件 API 版本 1.3
源控件插件 API 版本 1.3 引入了以下新函数，以提供更高级的控制。  
  
## <a name="changes"></a>更改  
 以下函数不熟悉源控制插件 API 版本 1.3:  
  
|函数|概述|  
|--------------|--------------|  
|[SccGetExtendedCapabilities](../../extensibility/sccgetextendedcapabilities-function.md)|允许其他功能位报告|  
|[SccEnumChangedFiles](../../extensibility/sccenumchangedfiles-function.md)|允许对文件中的本地磁盘上的版本控制数据库比具有较新版本的检查|  
|[SccQueryChanges](../../extensibility/sccquerychanges-function.md)|指定的文件，以允许对的名称更改 （重命名、 添加和删除操作） 的状态检查|  
|[SccPopulateDirList](../../extensibility/sccpopulatedirlist-function.md)|允许对目录和文件的版本控制数据库中的检查|  
|[SccAddFilesFromSCC](../../extensibility/sccaddfilesfromscc-function.md)|将指定的文件列表从版本控制数据库添加到当前项目|  
|[SccBackgroundGet](../../extensibility/sccbackgroundget-function.md)|执行无提示"获取"指定的文件 （没有用户界面显示）|  
|[SccGetUserOption](../../extensibility/sccgetuseroption-function.md)|允许访问特定于用户的选项|  
  
## <a name="see-also"></a>请参阅  
 [入门](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)   
 [源代码管理插件 API 版本 1.2 中的新增功能](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)