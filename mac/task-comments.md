---
title: 任务注释
description: ''
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 562DCB46-D8FA-4DC4-AAEA-F274448C4CD2
ms.openlocfilehash: c119af47cc3b592033a68b0ec543afa86140c77a
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="task-comments"></a>任务注释

编写代码时，标准做法是显式注释未完成代码、可疑代码或带有警告的快速解决方法。 Visual Studio for Mac 提供的默认信号令牌包括 TODO、HACK、FIXME 和 UNDONE。 可以在“Visual Studio”>“首选项...”>“环境”>“任务”下定义个性化令牌，如下图所示：

 ![任务列表首选项](media/source-editor-image10.png)

要添加新的任务注释，请添加包含任务关键字的注释。 例如:

```
//TODO: Finish this for all properties.
```

Visual Studio for Mac 通过在“任务列表”面板中突出显示这些标记提醒大家注意，可以通过导航到“视图”>“面板”>“任务”显示该面板：

![“任务列表”面板](media/source-editor-image11.png)