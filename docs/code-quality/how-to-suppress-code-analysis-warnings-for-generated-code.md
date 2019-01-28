---
title: 如何：禁止对生成的代码显示代码分析警告
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c6628692014cd495490384e8a707c23fdcb3bde
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55012945"
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>如何：禁止对生成的代码显示代码分析警告
托管的代码编译器通常会生成添加到项目，以便加快代码的开发的代码。 此外，开发人员通常使用第三方工具来帮助快速开发应用程序。 这些工具还生成添加到项目的代码。

 您可能想要看到的代码分析在生成的代码中发现的规则冲突。 但是，可能不想要查看它们是否不能查看和维护包含冲突的代码。

 **禁止显示生成代码的结果**项目的代码分析属性页上的复选框使您可选择是否想要查看从第三方工具生成的代码的代码分析警告。

> [!NOTE]
>  此选项不会取消代码分析错误和生成的代码时的错误和警告出现在窗体和模板。 可以查看和维护窗体或模板的源代码。

### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>若要禁止显示项目中生成代码的警告

1.  右键单击解决方案资源管理器中的项目，然后单击**属性**。

2.  单击**代码分析**。

3.  选择**禁止显示生成代码的结果**复选框。