---
title: 为所有（参数）添加 null 检查
ms.date: 07/24/2019
ms.topic: reference
author: stcahlon
ms.author: t-shzach
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: da3a616844dbe914cfe796ec35d1501bf83dd1ef
ms.sourcegitcommit: 3e74ec49a54e5c3da7631f4466128cdf4384af6b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "68712729"
---
# <a name="add-null-checks-for-all-parameters"></a>为所有参数添加 null 检查 

此重构适用于： 

- C# 

**功能：** 创建并添加用于检查所有可以为 null 的非选中参数是否为 null 的 `if` 语句。 

**使用时机：** 需要为所有适用的方法参数快速添加 null 检查。

操作原因：  编写多个参数的 null 检查可能会很耗时且重复。 使用此重构非常快捷，并使程序更可靠。  

## <a name="how-to"></a>操作说明 

1. 将光标置于方法中的任何参数上。

2. 按“Ctrl”  + **。** 触发“快速操作和重构”  菜单。

   ![快速操作和重构](media/add-null-checks-for-all-parameters.png)
   
3. 选择“为所有参数添加 null 检查”  选项。

   ![为所有添加 null 检查](media/add-null-checks-for-all.png) 

## <a name="see-also"></a>请参阅 

- [重构](../refactoring-in-visual-studio.md) 
