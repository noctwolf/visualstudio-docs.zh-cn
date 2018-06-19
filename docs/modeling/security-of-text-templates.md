---
title: 文本模板的安全性
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, security
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 71052a0d4120a74269f2aa05412230284271e574
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947516"
---
# <a name="security-of-text-templates"></a>文本模板的安全性
文本模板具有以下安全问题：

-   文本模板是任意代码插入到易受攻击。

-   如果主机用来查找指令处理器的机制不是安全的无法运行恶意的指令处理器。

## <a name="arbitrary-code"></a>任意代码
 当你需要编写一个模板时, 可以将之内的任何代码\<# # > 标记。 这允许从文本模板内部执行任意代码。

 请确保从可信的源获取模板。 请确保你的应用程序无法执行并非来自受信任源的模板的最终用户，则发出警告。

## <a name="malicious-directive-processor"></a>恶意的指令处理器
 与转换主机和一个或多个指令处理器转换到输出文件的模板文本，文本模板引擎进行交互。 有关详细信息，请参阅[文本模板转换过程](../modeling/the-text-template-transformation-process.md)。

 如果主机用来查找指令处理器的机制是不安全的它将运行运行恶意的指令处理器的风险。 恶意的指令处理器可以提供在中运行的代码`FullTrust`模式时运行该模板。 如果创建了自定义文本模板转换宿主，你必须使用一种安全机制，如注册表中，要找到指令处理器的引擎。