---
title: 生成 using
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 9fd34b40bdd1167eca7fa1dff8ab60bcc787b7c7
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57324752"
---
# <a name="generate-usings-in-visual-studio"></a>在 Visual Studio 中生成 using

此代码生成适用于：

- C#

**功能：****功能：** 可以立即添加复制和粘贴代码的必要导入或 [using 语句](/dotnet/csharp/language-reference/keywords/using-statement)。

**使用时机：** 通常的做法是从项目或其他代码源中的不同位置复制和粘贴代码。 此快速操作分析复制粘贴代码的缺少导入，然后提示添加它们。

操作原因：通过自动添加必要的导入，用户无需手动复制所需的 `using` 语句。

## <a name="generate-usings-refactoring"></a>生成 using 重构

1. 复制并粘贴来自其他文件的代码，无需包括必要的 `using` 语句。 现在，该错误附带添加缺少的 `using` 语句的代码修补程序。

    > [!NOTE] 
    > 需要在“工具”>“选项”>“文本编辑器”>“C#”>“高级”>“Using 指令”中打开此建议。

2. 按“Ctrl”+**。** 打开“快速操作和重构”菜单。 

    ![生成 using](media/generate-using-codefix.png)

3. 选择 **using \<your reference\>;** 以添加缺少的引用。

    ![生成 using 结果](media/generate-using-result.png)

## <a name="see-also"></a>请参阅

- [代码生成](../code-generation-in-visual-studio.md)
- [预览更改](../../ide/preview-changes.md)
- [针对 .NET 开发人员的提示](../../ide/visual-studio-2017-for-dotnet-developers.md)