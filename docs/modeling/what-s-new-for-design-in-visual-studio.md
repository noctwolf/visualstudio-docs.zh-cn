---
title: Visual Studio 中用于设计的新增功能
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
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
ms.openlocfilehash: c25d89ae3ab3d25e415b4407a46fc903b1c05266
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33870957"
---
# <a name="whats-new-for-design-in-visual-studio"></a>Visual Studio 中用于设计的新增功能

## <a name="live-dependency-validation"></a>实时依赖关系验证

删除不需要的依赖关系是管理技术债务的重要组成部分。 依赖项的实时验证现在包含，提供有关问题，精确的信息，并完全获益错误列表和编辑器中的新功能。

![在操作中的实时依赖关系验证](media/dep-validation-whatsnew-01.png)

已更改的创作体验，以使依赖项验证更容易地发现、 更易于访问，更改到"依赖项关系图"从"层关系图"术语。

**体系结构**菜单现在包含直接创建依赖项关系图的命令：

![体系结构菜单上的实时依赖项](media/dep-validation-whatsnew-02.png)

...和中层依赖项关系图中和及其说明的属性名称已更改，以使它们更有意义：

![实时更新的依赖项属性名称](media/dep-validation-whatsnew-03.png)

现在，你看到立即在解决方案中的当前代码分析结果中所做的更改的影响每次保存关系图。 你无需再等待完成"验证依赖关系"命令。

有关更多详细信息，请参阅[这篇博客文章](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/07/live-architecture-dependency-validation-in-visual-studio-15-preview-5/)。

## <a name="uml-designers-have-been-removed"></a>已删除 UML 设计器

已从 Visual Studio Enterprise 的此版本中删除的 UML 设计器。

* UML 关系图现在显示为 XML 文件
* UML 模型资源管理器不再存在
* 建模的项目引用不再用于依赖关系验证
* 不再显示解决方案资源管理器中的"层引用"节点
* 不再使用依赖项 （层） 关系图上的"验证"生成操作-已删除的生成任务
* 为版本之间的往返维护的项目结构
* 你可以仍打开、 创建、 编辑和保存为 XML 的依赖项 （层） 关系图
* TFS 工作项链接到依赖项 （层） 关系图不是可在设计图面上访问
* 不再支持后从链接到 DSL 或图层
* 不再支持 UML 建模 SDK 的可扩展性

但是，支持可通过可视化.NET 和 c + + 代码的体系结构为[代码图](map-dependencies-across-your-solutions.md)，和的依赖项验证上面所述的重大改进。

如果你的 UML 设计器的大量用户，你可以继续使用 Visual Studio 2015 或更早版本，而你决定备用工具对于你的 UML 需求。

有关更多详细信息，请参阅[这篇博客文章](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/14/uml-designers-have-been-removed-layer-designer-now-supports-live-architectural-analysis/)。

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="a-nameversionsupport-version-support-for-architecture-and-modeling-tools"></a><a name="VersionSupport" />对体系结构和建模工具版本支持

Visual Studio 2015 是有多个版本。 不是所有这些体系结构和建模工具提供支持。 下表显示每个工具的可用性。

|**功能**|**Enterprise**|**Professional**|**Community**|**Express**|
|-----------------|--------------------|----------------------|-------------------|-----------------|
|**代码图**|是|仅支持读取代码图，筛选代码映射时，添加新的泛型节点以及从所选内容创建新的定向关系图。|-|-|
|**依赖项关系图**|是|仅支持读取依赖项关系图。|仅支持读取依赖项关系图。|-|
|**定向关系图**（DGML 关系图）|是|是|是|-|
|**代码克隆**|是|-|-|-|