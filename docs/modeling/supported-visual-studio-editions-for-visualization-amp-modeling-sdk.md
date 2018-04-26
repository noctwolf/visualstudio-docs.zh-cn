---
title: 支持的可视化效果的 Visual Studio 版本&amp;建模 SDK
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools, supported Visual Studio editions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 004a6b75bb66ebf3c1797abac9c1cc6f7faa6eb9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="supported-visual-studio-editions-for-visualization-amp-modeling-sdk"></a>支持的可视化效果的 Visual Studio 版本&amp;建模 SDK
以下是一系列 Visual Studio 版本支持用于[!INCLUDE[dsl](../modeling/includes/dsl_md.md)]的创作和部署环境中。 有关这些版本的详细信息，请参阅 Microsoft [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] [开发人员中心](http://go.microsoft.com/fwlink/?LinkId=75628)。

## <a name="authoring-edition"></a>创作版
 若要定义 DSL，必须安装以下组件：

|||
|-|-|
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|Visual Studio SDK|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|Visual Studio 可视化和建模 SDK|[http://go.microsoft.com/fwlink/?LinkID=186128](http://go.microsoft.com/fwlink/?LinkID=186128)|

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="deployment-editions"></a>部署版
 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 支持以下用于部署生成的域特定语言的配置：

-   Visual Studio Enterprise

-   Visual Studio Professional

-   Visual Studio Shell （集成模式下） 可再发行组件包可再发行组件包

-   Visual Studio Shell（独立模式）可再发行组件包

> [!NOTE]
>  若要使 DSL 能够 Shell 产品上运行，必须设置**支持 VS 版本**扩展清单中的字段。 有关详细信息，请参阅[部署域特定语言解决方案](../modeling/deploying-domain-specific-language-solutions.md)。

## <a name="see-also"></a>请参阅

- [域特定语言工具词汇表](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
