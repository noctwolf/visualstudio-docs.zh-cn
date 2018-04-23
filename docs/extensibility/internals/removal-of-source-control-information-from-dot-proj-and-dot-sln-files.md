---
title: 从源代码管理信息的删除操作。Proj 和。Sln 文件 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, .sln and .proj files
ms.assetid: 7b06883f-35de-41e2-9a9e-d3edba236f17
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 695a4ccfc5da20bda25c78929488625c244959a8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="removal-of-source-control-information-from-proj-and-sln-files"></a>从源代码管理信息的删除操作。Proj 和。Sln 文件
在版本 1.2 的源控制插件 API SCC 信息存储在 MSSCCPRJ。SCC 文件。 MSSCCPRJ 的优点。SCC 文件是 SCC 信息是源不的控制，像.proj 和.sln 文件。  
  
## <a name="version-12-changes"></a>1.2 版更改  
 在源控件插件基于源控件插件 API 版本 1.1，关于版本控制的信息存储在项目 (.proj) 和解决方案 (.sln) 文件。 源代码管理信息的数据库位置指定的 AuxPath，，ProjName 指定数据库中的特定位置。 此行为可能会问题导致分支、 分叉或复制操作之后，因为 ProjName 通常将在任何这些操作后无效。  
  
 在源控件插件 API 版本 1.1，IDE 使用 ~ SAK 文件以检测如果插件支持 MSSCCPRJ。SCC 存储源代码管理信息的方法。 源控件插件 API 版本 1.2 提供新功能，用于检测 MSSCCPRJ 的支持。SCC 文件而无需使用 ~ SAK 文件。 有关详细信息，请参阅[消除了 ~ SAK 文件](../../extensibility/internals/elimination-of-tilde-sak-files.md)。  
  
## <a name="see-also"></a>另请参阅  
 [源代码管理插件 API 版本 1.2 中的新增功能](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)