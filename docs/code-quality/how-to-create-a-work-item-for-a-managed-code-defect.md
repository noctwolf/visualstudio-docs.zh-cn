---
title: 如何：为托管代码缺陷创建工作项
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- managed code, creating work items for code defects
- code analysis, creating work items
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: b251970bfd57b31842e1573e2e156e11a517c81a
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279468"
---
# <a name="how-to-create-a-work-item-for-a-managed-code-defect"></a>如何：为托管代码缺陷创建工作项

可以使用从 Visual Studio 中的记录工作项的工作项跟踪功能。 若要使用此功能，你的项目必须是 Azure DevOps 项目中的一部分[!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)]。

## <a name="to-create-a-work-item-for-managed-code-defect"></a>若要创建托管的代码缺陷的工作项

1. 在中**代码分析**窗口中，选择警告。

2. 选择**操作**，然后选择**创建工作项**，然后选择要创建的工作项类型。

     您指定的缺陷信息创建新工作项。

## <a name="to-create-a-work-item-for-multiple-managed-code-defects"></a>若要创建多个托管的代码缺陷的工作项

1. 在中**错误列表**、 选择多个警告，然后右键单击出现的警告。

2. 指向**创建工作项**，并单击要创建的工作项类型。

     为所有选定的警告，以指定 bug 信息创建一个工作项。