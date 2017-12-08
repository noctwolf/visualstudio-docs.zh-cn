---
title: "条件编译 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ConditionalComp_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- conditional compilation, overview
- conditional compilation
ms.assetid: a843de4e-3aae-43cd-ad64-477dd00814a2
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6d6a5987b21afcab8c62a609dfba33f963d544de
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="conditional-compilation-javascript"></a>条件编译 (JavaScript)
利用条件编译，可以使用新的 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 语言功能，同时又保留与不支持这些功能的旧版本之间的兼容性。  
  
> [!WARNING]
>  Internet Explorer 11 之前的所有版本的 Internet Explorer 都支持条件编译。 从 Internet Explorer 11 标准模式开始，[!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)]应用不支持条件编译。  
  
## <a name="statements"></a>语句  
 可通过使用 `@cc_on` 语句或者使用 `@if` 或 `@set` 语句来激活条件编译。 条件编译的一些典型用途包括在 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 中使用新功能、将调试支持嵌入到脚本中以及跟踪代码执行。  
  
 始终将条件编译代码放置在注释中，以便不支持条件编译的主机（如 Netscape Navigator）将其忽略。 这是一个示例。  
  
```JavaScript  
/*@cc_on @*/  
/*@if (@_jscript_version >= 4)  
    alert("JavaScript version 4 or better");  
    @else @*/  
    alert("Conditional compilation not supported by this scripting engine.");  
/*@end @*/  
```  
  
 此示例使用特殊的注释分隔符，仅在 `@cc_on` 语句激活条件编译后使用这些分隔符。 不支持条件编译的脚本引擎仅看到表明不支持条件编译的消息。