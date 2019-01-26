---
title: 扩展依赖项关系图
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 04aa7c1948cd07bf49ab754619442e5310b023f9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55069129"
---
# <a name="extend-dependency-diagrams"></a>扩展依赖项关系图
您可以编写代码以创建和更新依赖项关系图，并验证应用程序代码对 Visual Studio 中的依赖项关系图的结构。 可以添加显示在关系图的快捷（上下文）菜单上的命令、自定义拖放笔势并从文本模板访问层模型的命令。 可以将这些扩展打包到 Visual Studio 集成扩展 (VSIX) 中，并将其分发给其他 Visual Studio 用户。

 有关依赖项关系图的详细信息，请参阅：

-   [依赖项关系图：引用](../modeling/layer-diagrams-reference.md)

-   [依赖项关系图：指导原则](../modeling/layer-diagrams-guidelines.md)

-   [从代码创建依赖项关系图](../modeling/create-layer-diagrams-from-your-code.md)

-   [使用依赖项关系图验证代码](../modeling/validate-code-with-layer-diagrams.md)

##  <a name="prereqs"></a> 要求
 必须在想要开发层扩展的计算机上安装了以下内容：

-   Visual Studio

-   [Visual Studio SDK](../extensibility/visual-studio-sdk.md)

-   Visual Studio 的建模 SDK


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]


 在想要运行层扩展的计算机上必须安装合适版本的 Visual Studio。 有关详细信息，请参阅[部署层模型扩展](../modeling/deploy-a-layer-model-extension.md)。

 若要查看支持的 Visual Studio 版本的依赖项关系图，请参阅[体系结构和建模工具的版本支持](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)。

## <a name="in-this-section"></a>本节内容
 [向依赖项关系图添加命令和手势](../modeling/add-commands-and-gestures-to-layer-diagrams.md)

 [向依赖项关系图添加自定义体系结构验证](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)

 [向依赖项关系图添加自定义属性](../modeling/add-custom-properties-to-layer-diagrams.md)

 [在程序代码中导航和更新层模型](../modeling/navigate-and-update-layer-models-in-program-code.md)

 [部署层模型扩展](../modeling/deploy-a-layer-model-extension.md)

 [依赖项关系图扩展疑难解答](../modeling/troubleshoot-extensions-for-layer-diagrams.md)

## <a name="see-also"></a>请参阅

- [依赖项关系图：引用](../modeling/layer-diagrams-reference.md)
- [依赖项关系图：指导原则](../modeling/layer-diagrams-guidelines.md)
- [从代码创建依赖项关系图](../modeling/create-layer-diagrams-from-your-code.md)
- [使用依赖项关系图验证代码](../modeling/validate-code-with-layer-diagrams.md)
