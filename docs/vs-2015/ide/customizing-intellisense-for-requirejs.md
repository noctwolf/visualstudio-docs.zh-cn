---
title: 为 RequireJS 自定义 IntelliSense |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2be07ef8-9c08-444b-a21a-22a4fe6386a3
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fbc4d9b85a3eb8e0fe5f3a890a76bae4695912e4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468772"
---
# <a name="customizing-intellisense-for-requirejs"></a>为 RequireJS 自定义 IntelliSense
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[Visual Studio 2017 文档](https://docs.microsoft.com/en-us/visualstudio/)。  
  
从 Visual Studio 2013 Update 4 开始，支持对常用 RequireJS JavaScript 文件和模块化加载程序的支持。 RequireJS 使定义代码模块之间的依赖关系和仅在需要时动态加载模块更容易了。 编写使用 RequireJS 的 JavaScript 代码时，会针对你从你的模块定义中引用的模块或通过调用 `require()` 从你的代码中引用的模块提供 IntelliSense 建议。  
  
 默认情况下，Visual Studio 支持非常基本的配置，以支持 RequireJS，但常见的做法是设置你自己的自定义配置设置（即为库定义别名）。 本主题介绍可用于自定义 Visual Studio 几种不同方法，以用于你的项目的独特设置。  
  
 本主题描述了如何执行以下操作：  
  
-   在 ASP.NET 项目中自定义 RequireJS  
  
-   在 JSProj 项目中自定义用于生成 Apache Cordova 应用、Windows 应用商店应用和 LightSwitch HTML 应用的 RequireJS  
  
## <a name="customize-requirejs-in-aspnet-projects"></a>在 ASP.NET 项目中自定义 RequireJS  
 你当前的 JavaScript 文件引用名为 require.js 的文件时，会自动启用对 RequireJS 的支持 (有关详细信息，请参阅中的确定 IntelliSense 上下文部分[JavaScript IntelliSense](../ide/javascript-intellisense.md))。 在 ASP.NET 项目中引用 require.js 通常是使用的 / /\<引用 / > 指令 _references.js 文件中。  
  
### <a name="configure-the-data-main-attribute-in-an-aspnet-project"></a>在 ASP.NET 项目中配置 data-main 属性  
 为了准确地模拟运行应用时应用的工作情况，JavaScript 编辑器需要知道在设置 require.js 时应首先加载什么文件。 通常使用引用 require.js 的脚本元素上的 `data-main` 属性在你的应用程序 HTML 文件中对此进行配置，如下所示。  
  
```html  
<script src="js/require.js" data-main="js/app.js"></script>  
```  
  
 在此示例中，data-main (js/app.js) 引用的脚本在 require.js 后立即加载。 立即加载的文件是首次配置 RequireJS 使用情况的最佳位置 (使用`require.config()`)。要用于哪些文件告知 JavaScript 编辑器`data-main`在应用程序中，添加`data-main`属性，并修改的 / /\<引用 / > 你的应用程序中引用 require.js 的指令。 例如，可以使用以下指令：  
  
```javascript  
/// <reference path="js/require.js" data-main="js/app.js" />  
```  
  
### <a name="configure-the-application-start-page-in-an-aspnet-project"></a>在 ASP.NET 项目中配置应用程序起始页  
 应用运行时，RequireJS 假设的相对文件路径 (例如，"...\\"路径） 是相对于加载 require.js 库的 HTML 文件。 在 Visual Studio 编辑器中编写 ASP.NET 项目的代码时，此起始页是未知的，你需要告知编辑器使用相对文件路径时要使用什么起始页。 若要执行此操作，添加`start-page`属性为 / /\<引用 / > 指令。  
  
```javascript  
/// <reference path="js/require.js" data-main="js/app.js" start-page="/app/index.html" />  
```  
  
 `start-page` 属性指定运行应用时在浏览器中看到的页面的 URL。  
  
## <a name="customize-requirejs-in-jsproj-projects"></a>在 JSProj 项目中自定义 RequireJS  
 生成 Apache Cordova 应用、基于 HTML 的 Windows 应用商店应用或 LightSwitch HTML 应用时，使用 JSProj 项目（项目文件以 .jsproj 扩展名结尾）。 与 ASP.NET 项目不同，这些项目从项目中存在的 HTML 文件读取对 .js 文件的引用。 因此，在 JSProj 项目中编辑 JavaScript 时，你将看到，如果当前正在编辑 JavaScript 文件在另一个也引用 require.js 的 HTML 文件中被引用，将启用对 RequireJS 的支持。  
  
 JSProj 项目文件中不需要 ASP.NET 项目所需的自定义步骤。 也就是说，会自动加载引用 require.js 的脚本标记上的 `data-main` 属性使用的脚本文件以配置 require.js。 引用 require.js 的 HTML 文件还用作应用程序的起始页。  
  
## <a name="see-also"></a>请参阅  
 [JavaScript IntelliSense](../ide/javascript-intellisense.md)



