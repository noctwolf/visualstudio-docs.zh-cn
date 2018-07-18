---
title: 持久性和运行记录表 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- persistence, managing
- IVsPersistHierarchyItem interface, implementing
- architecture, persistence
- running document table (RDT), architecture
ms.assetid: 27117eae-6c58-4189-a61a-1397a43b5ecf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 51f3d2cc41c9adaf97215701ad01da2e59d245a8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129730"
---
# <a name="persistence-and-the-running-document-table"></a>持久性和运行文档表
在[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]IDE，项目将完全负责管理他们完成使用服务，其项目项的持久性<xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>。 文档是持久性的在 Visual Studio 环境中的基本单位。 项目协调打开、 保存和重命名的文档与正在运行文档表 (RDT) 跟踪所有打开的文档的状态的资源。  
  
## <a name="managing-persistence"></a>管理持久性  
 项目控制通过实现环境的持久性服务<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem>接口。 虽然环境永远不会直接请求时要保留本身的文档，它会请求所属项目 （或层次结构） 保存文档。 这使得其项目项数据保存到本地文件、 远程文件、 数据库、 一个存储库或其他媒体的项目。  
  
 全局环境负责维护 RDT。 环境负责维护所有打开的窗口的条目和 RDT，这样就可以为它们到中的文档接收特殊的通知，如关闭解决方案时。 此外，RDT 使环境来跟踪在其相应节点**解决方案资源管理器**。 RDT 维护每个打开的、 持久的对象，包括项目文件和项目项文档的一条记录。  
  
## <a name="see-also"></a>另请参阅  
 [正在运行的文档表](../../extensibility/internals/running-document-table.md)   
 [IDE 中的选择和货币](../../extensibility/internals/selection-and-currency-in-the-ide.md)