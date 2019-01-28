---
title: 如何：创建托管代码缺陷的工作项
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- managed code, creating work items for code defects
- code analysis, creating work items
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 1cb63612194148b5f3ea1f90d7c57e59fb84edbc
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54941822"
---
# <a name="how-to-create-a-work-item-for-a-managed-code-defect"></a>如何：创建托管代码缺陷的工作项

可以使用从 Visual Studio 中的记录工作项的工作项跟踪功能。 若要使用此功能，你的项目必须是 Azure DevOps 项目中的一部分[!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)]。

## <a name="to-create-a-work-item-for-managed-code-defect"></a>若要创建托管的代码缺陷的工作项

1. 在中**代码分析**窗口中，选择警告。

2. 选择**操作**，然后选择**创建工作项**，然后选择要创建的工作项类型。

     您指定的缺陷信息创建新工作项。

## <a name="to-create-a-work-item-for-multiple-managed-code-defects"></a>若要创建多个托管的代码缺陷的工作项

1. 在中**错误列表**、 选择多个警告，然后右键单击出现的警告。

2. 指向**创建工作项**，并单击要创建的工作项类型。

     为所有选定的警告，以指定 bug 信息创建一个工作项。