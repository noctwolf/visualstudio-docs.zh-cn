---
title: FxCopCmd 错误 |Microsoft 文档
ms.date: 10/19/2016
ms.technology: vs-ide-code-analysis
ms.topic: article
helpviewer_keywords:
- FxCopCmd errors
ms.assetid: bb614ed0-1b7c-4b56-99ae-da50ef6cfef9
ms.author: gewarren
author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b407167a772a82b56c39ba222dc3c1f563f5c012
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="fxcopcmd-tool-errors"></a>FxCopCmd 工具错误

FxCopCmd 不考虑所有错误都以是致命的。 如果 FxCopCmd 具有足够的信息来执行部分分析，它将执行的分析和报告的错误的发生。 错误代码，它是一个 32 位整数，包含对应于错误的数字值的按位组合。

下表介绍 FxCopCmd 返回的错误代码：

|Error|数字值|
|-----------|-------------------|
|没有错误|0x0|
|分析错误|0x1|
|规则例外|0x2|
|项目加载错误|0x4|
|程序集加载错误|0x8|
|规则库加载错误|0x10|
|导入报表加载错误|0x20|
|输出错误|0x40|
|命令行开关错误|0x80|
|初始化错误|0x100|
|程序集引用错误|0x200|
|BuildBreakingMessage|0x400|
|未知的错误|0x1000000|

**分析错误**为严重错误返回。 它指示无法完成分析。 如果适用，错误代码还包含错误的根本原因。 以下情况下将生成错误：

- 由于输入不足，无法执行分析。

- 分析引发了 FxCopCmd 未处理的异常。

- 指定的项目文件未找到或者已损坏。

- 未指定输出选项，或无法写入文件。

> [!NOTE]
> FxCopCmd 返回代码**程序集引用错误**0x200 本身是一个警告，而不是错误。 此返回代码指示缺少的间接引用，但该 FxCopCmd 已能够处理它们。 此警告意味着某些分析结果可能已泄露的可能性。 将**程序集引用错误**为错误时它与任何其他返回代码相结合。

## <a name="see-also"></a>请参阅

- [代码分析应用程序错误](../code-quality/code-analysis-application-errors.md)