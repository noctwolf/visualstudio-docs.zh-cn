---
title: 跨多个项目连接设置的应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, application of settings
ms.assetid: 2116d3d0-c46c-4d0a-b482-08a178584f46
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cc2be78900e7bef33be138dfc8ed9dc1531af7c8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470145"
---
# <a name="application-of-settings-across-multiple-project-connections"></a>跨多个项目连接应用设置
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[应用程序的设置跨多个项目连接](https://docs.microsoft.com/visualstudio/extensibility/internals/application-of-settings-across-multiple-project-connections)。  
  
源代码管理插件使用源控件的插件 API 1.2 中，生成可用于批处理操作执行相同的源代码管理操作跨多个项目或多个连接上下文。 若要消除冗余，每个项目对话框从用户体验，可以使用批处理。  
  
 如果用户选择多个项属于使用源控制插件 API 1.1 （例如，在不同的文件共享计算机上两个 Web 项目） 生成的源代码管理插件中的多个连接，并检查它们，用户将看到相同的对话框重复。 即使用户单击发生这种情况**应用到所有**中的复选框的对话框中，因为 IDE 将重置其状态，以便每个连接上下文。  
  
## <a name="new-capability-flag"></a>新的功能标志  
 `SccBeginBatch` 函数集`SCC_CAP_BATCH`标志，用于指示批处理操作正在进行  
  
## <a name="new-functions"></a>新的函数  
 以下新函数支持批处理操作：  
  
-   [SccBeginBatch](../../extensibility/sccbeginbatch-function.md)  
  
-   [SccEndBatch](../../extensibility/sccendbatch-function.md)  
  
 `SCCBeginBatch`函数启动的源代码管理操作组。 `SccEndBatch` 关闭组。 不能嵌套组。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 版本 1.2 中的新增功能](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)

