---
title: 从源代码管理信息的删除操作。Proj 和。Sln 文件 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, .sln and .proj files
ms.assetid: 7b06883f-35de-41e2-9a9e-d3edba236f17
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1cd49b27804e35e28395c78a6e177db1461a54f4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54943365"
---
# <a name="removal-of-source-control-information-from-proj-and-sln-files"></a>删除 .Proj 和 .Sln 文件中的源代码管理信息
在版本 1.2 的源控制插件 API SCC 的信息存储在 MSSCCPRJ。SCC 文件。 MSSCCPRJ 的优点。SCC 文件是 SCC 信息是源不的控制，就像在.proj 和.sln 文件中。  
  
## <a name="version-12-changes"></a>1.2 版的更改  
 在源控件的管理单元基于源控制插件 API 版本 1.1 中，源控件的信息存储在项目 (.proj) 和解决方案 (.sln) 文件。 源代码管理信息的数据库位置指定由 AuxPath，并由项目名称指定数据库中的特定位置。 此行为可能分支、 分支或复制操作后导致的问题，因为 ProjName 通常将上述任何操作后无效。  
  
 在源控件插件 API 版本 1.1 中，IDE 使用 ~ SAK 文件以检测如果插件支持 MSSCCPRJ。源代码管理存储的源代码管理信息的方法。 源控件插件 API 1.2 版提供了一项新功能用于检测 MSSCCPRJ 的支持。SCC 文件而无需使用 ~ SAK 文件。 有关详细信息，请参阅[消除了 ~ SAK 文件](../../extensibility/internals/elimination-of-tilde-sak-files.md)。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 版本 1.2 中的新增功能](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)