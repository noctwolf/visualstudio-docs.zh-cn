---
title: 为托管代码的全球化规则规则设置 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: 3c4032ee-0805-4581-8c48-b1827cd6b213
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 54e1df6f8c49112747ccd7254f01a57d33dccf0e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="globalization-rules-rule-set-for-managed-code"></a>托管代码的“全球化规则”规则集
你可以使用的 Microsoft 全球化规则规则集重点解决问题，可能会阻止从以不同语言、 区域设置中和区域文化正确显示应用程序中的数据。 你应包含此规则集如果本地化你的应用程序，则全球化，或两个。  
  
|规则|描述|  
|----------|-----------------|  
|[CA1300](../code-quality/ca1300-specify-messageboxoptions.md)|指定 MessageBoxOptions|  
|[CA1301](../code-quality/ca1301-avoid-duplicate-accelerators.md)|避免快捷键重复|  
|[CA1302](../code-quality/ca1302-do-not-hardcode-locale-specific-strings.md)|不要对区域设置特定的字符串|  
|[CA1303](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)|不要将文本作为本地化参数传递|  
|[CA1304](../code-quality/ca1304-specify-cultureinfo.md)|指定 CultureInfo|  
|[CA1305](../code-quality/ca1305-specify-iformatprovider.md)|指定 IFormatProvider|  
|[CA1306](../code-quality/ca1306-set-locale-for-data-types.md)|数据类型的设置区域设置|  
|[CA1307](../code-quality/ca1307-specify-stringcomparison.md)|指定 StringComparison|  
|[CA1308](../code-quality/ca1308-normalize-strings-to-uppercase.md)|将字符串规范化为大写|  
|[CA1309](../code-quality/ca1309-use-ordinal-stringcomparison.md)|使用序号 StringComparison|  
|[CA2101](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|指定对 P/Invoke 字符串自变量进行封送处理|