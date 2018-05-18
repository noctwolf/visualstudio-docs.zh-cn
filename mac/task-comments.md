---
title: 任务注释
description: 将任务注释添加到代码
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 562DCB46-D8FA-4DC4-AAEA-F274448C4CD2
ms.openlocfilehash: ca74c6429ed721a6c11bd71d024668cc695274e9
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
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