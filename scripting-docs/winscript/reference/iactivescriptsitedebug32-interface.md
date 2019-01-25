---
title: IActiveScriptSiteDebug32 Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03f42217-303d-46e7-9792-61a5ab95252c
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: e7937311e01274570e34bd639a0dc5f68206a3aa
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345560"
---
# <a name="iactivescriptsitedebug32-interface"></a>IActiveScriptSiteDebug32 Interface
智能主机实现`IActiveScriptSiteDebug32`界面，用于执行文档管理和参与调试。 `IActiveScriptSite`对象通常提供的实现`IActiveScriptSiteDebug32`接口。 如果此操作后，调用`IActiveScriptSite::QueryInterface`方法来获取`IActiveScriptSiteDebug32`接口。  
  
 除了继承的方法之外`IUnknown`，则`IActiveScriptSiteDebug32`接口公开以下方法。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IActiveScriptSiteDebug32::GetApplication](../../winscript/reference/iactivescriptsitedebug32-getapplication.md)|返回与此脚本站点关联的调试应用程序对象。|  
|[IActiveScriptSiteDebug32::GetDocumentContextFromPosition](../../winscript/reference/iactivescriptsitedebug32-getdocumentcontextfromposition.md)|语言引擎用于委派`IDebugCodeContext::GetSourceContext`。|