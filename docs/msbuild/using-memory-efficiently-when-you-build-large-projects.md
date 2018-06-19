---
title: 在生成大型项目时有效使用内存 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 386a15bb0eb1d4fb88a89fc3683b7e0bdc088d6e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
ms.locfileid: "31568053"
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>在生成大型项目时有效使用内存
大型项目通常包含许多子项目和其他依赖项，并且它们可能会在生成时占用大量系统内存。 当可用系统内存减少时，系统性能可能也会降低。 较旧版本的 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 项目保留在内存中，或者 3.5 版中的项目会被删除，但会在缓存中保留生成结果，供将来检索。  
  
 4.0 版会自动处理此内存管理，项目无需使用 `UnloadProjectsOnCompletion` 和 `UseResultsCache` 等属性。  
  
## <a name="see-also"></a>请参阅  
 [并行生成多个项目](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)