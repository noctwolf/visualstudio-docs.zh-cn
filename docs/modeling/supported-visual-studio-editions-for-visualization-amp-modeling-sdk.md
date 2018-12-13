---
title: 可视化和建模 SDK 支持 Visual Studio 版本
titleSuffix: ''
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
ms.openlocfilehash: 65014d8c697adbf5fb8e13d28708090360bb9c17
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53049941"
---
# <a name="supported-visual-studio-editions-for-visualization--modeling-sdk"></a>可视化和建模 SDK 支持的 Visual Studio 版本

以下是支持与 Visual Studio 版本的列表[!INCLUDE[dsl](../modeling/includes/dsl_md.md)]中创作和部署环境。 有关这些版本的详细信息，请参阅 Microsoft Visual Studio[开发人员中心](http://go.microsoft.com/fwlink/?LinkId=75628)。

## <a name="authoring-edition"></a>创作版

若要定义 DSL，必须安装以下组件：

|||
|-|-|
|Visual Studio|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|Visual Studio SDK|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|Visual Studio 可视化和建模 SDK|[http://go.microsoft.com/fwlink/?LinkID=186128](http://go.microsoft.com/fwlink/?LinkID=186128)|

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="deployment-editions"></a>部署版

[!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 支持以下用于部署生成的域特定语言的配置：

-   Visual Studio Enterprise

-   Visual Studio Professional

-   Visual Studio Shell （集成模式） 可再发行组件包可再发行组件包

-   Visual Studio Shell（独立模式）可再发行组件包

> [!NOTE]
> 若要使 DSL 能够在 Shell 产品上运行，必须设置**支持的 VS 版本**字段在扩展清单中。 有关详细信息，请参阅[部署域特定语言解决方案](../modeling/deploying-domain-specific-language-solutions.md)。

## <a name="see-also"></a>请参阅

- [域特定语言工具术语表](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)