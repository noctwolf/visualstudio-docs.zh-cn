---
title: 什么是设计的新增功能
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- what's new [VIsual Studio ALM], architecture and modeling
- architecture [Visual Studio Ultimate], modeling
- modeling software [Visual Studio ALM], What's New
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bdea0b8e24347e608ad0e1736b55e34acb4e5854
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53956018"
---
# <a name="whats-new-for-design-in-visual-studio"></a>Visual Studio 中用于设计的新增功能

## <a name="live-dependency-validation"></a>实时依赖项验证

删除不需要的依赖项是管理技术债务的重要组成部分。 依赖项的实时验证现在包含，提供有关问题的精确信息，并完全受益于错误列表和在编辑器中的新功能。

![操作中的实时依赖项验证](media/dep-validation-whatsnew-01.png)

创作体验已更改，以使依赖项验证更容易地发现、 更易于访问，更改到"依赖项关系图"从"层关系图"术语。

**体系结构**菜单现在包含直接创建依赖项关系图的命令：

![实时依赖项的体系结构菜单项](media/dep-validation-whatsnew-02.png)

...和层的依赖项关系图和及其说明的属性名称已更改，以使其更有意义：

![更新的实时依赖项属性名称](media/dep-validation-whatsnew-03.png)

您现在看到立即在当前解决方案中的代码分析结果中的更改的影响每次保存关系图。 您无需再等待完成的"验证依赖项"命令。

有关更多详细信息，请参阅[这篇博客文章](https://blogs.msdn.microsoft.com/devops/2016/10/07/live-architecture-dependency-validation-in-visual-studio-15-preview-5/)。

## <a name="uml-designers-have-been-removed"></a>已删除 UML 设计器

UML 设计器已从 Visual Studio Enterprise 的此版本中删除。

* UML 关系图现在显示为 XML 文件
* UML 模型资源管理器不再存在
* 建模的项目引用不能再用于依赖项验证
* 不再显示在解决方案资源管理器中的"层引用"节点
* 不再使用依赖项 （层） 关系图上的"验证"生成操作-已删除生成任务
* 为版本之间的往返维护项目结构
* 您可以仍打开、 创建、 编辑和将依赖项 （层） 关系图另存为 XML
* TFS 工作项链接到依赖项 （层） 关系图不能访问在设计图面上
* 不再支持后从链接到 DSL 或图层
* 不再支持 UML 建模 SDK 的可扩展性

但是，对可视化.NET 和 c + + 代码的体系结构是可通过支持[代码映射](map-dependencies-across-your-solutions.md)，和依赖项验证上面所述的重大改进。

如果您是 UML 设计器的大量用户，你可以继续使用 Visual Studio 2015 或更早版本，而 UML 需要确定一种备选工具。

有关更多详细信息，请参阅[这篇博客文章](https://blogs.msdn.microsoft.com/devops/2016/10/14/uml-designers-have-been-removed-layer-designer-now-supports-live-architectural-analysis/)。

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="a-nameversionsupport-edition-support-for-architecture-and-modeling-tools"></a><a name="VersionSupport" />对体系结构和建模工具的版本支持

Visual Studio 2017 现已推出多个版本。 并非所有这些体系结构和建模工具提供支持。 下表显示每个工具的可用性。

|**功能**|**企业版**|**专业版**|**社区版**|
|-|-|-|-|
|**代码图**|是|仅支持读取代码图，筛选代码映射时，添加新的泛型节点和从所选内容创建新的定向关系图。|-|
|**依赖项关系图**|是|仅支持读取依赖项关系图。|仅支持读取依赖项关系图。|
|**定向关系图**（DGML 关系图）|是|是|是|
|**代码克隆**|是|-|-|