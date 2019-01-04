---
title: VS Shell 部署
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 2d732b050a9f12b6324abaf253739cd4f3e223aa
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53914483"
---
# <a name="vs-shell-deployment"></a>VS Shell 部署

独立的 shell，可以确定哪些 Visual Studio 需要与域特定语言以及如何显示该解决方案应进行交互的功能。 有关 Visual Studio 独立 shell 的详细信息，请参阅[自定义独立 Shell](https://vspartner.com/pages/vsshells)。

若要作为部署目标设置 Visual Studio Shell:

1. 在中**DslPackage**项目中，打开**source.extension.tt**。

2. 下`<SupportedProducts>`插入：

   ```xml
   <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>
   ```

   替换*MyIsolatedShell*与独立的 shell 包的名称。