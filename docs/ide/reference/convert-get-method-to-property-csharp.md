---
title: "将 Get 方法转换为属性并将属性转换为 Get 方法 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
ms.devlang: csharp
author: kuhlenh
ms.author: kaseyu
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.convertmethodtoproperty
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: a23af31c5099908ed0b6fed07404216a57975f75
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2018
---
# <a name="convert-get-method-to-property--convert-property-to-get-method"></a>将 Get 方法转换为属性 / 将属性转换为 Get 方法

## <a name="convert-get-method-to-property"></a>将 Get 方法转换为属性

功能：将 Get 方法转换为属性（或 Set 方法），反之亦然。

时机：有不包含任何逻辑的 Get 方法时。

方法：

1. 将光标置于 Get 方法名称中。

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“用属性替换方法”。 如果你有一个 Set 方法，此时还可以通过选择“用属性替换 Get 方法和 Set 方法”来转换 Set 方法。
   * **鼠标**
     * 右键单击代码，选择“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“用属性替换方法”。 如果你有一个 Set 方法，此时还可以通过选择“用属性替换 Get 方法和 Set 方法”来转换 Set 方法。

1. 如果对代码预览中的更改感到满意，请按“Enter”或单击菜单中的“修复”，即可提交所做的更改。

示例:

```csharp
private int MyValue;

// Before
public int GetMyValue()
{
    return MyValue;
}

// Replace 'GetMyValue' with property

// After
public int MyValue
{
    get { return MyValue; }
}
```

## <a name="convert-property-to-get-method"></a>将属性转换为 Get 方法

功能：将属性转换为 Get 方法

时机：有涉及多个立即设置或获取值的属性时 

方法：

1. 将光标置于 Get 方法名称中。

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“用方法替换属性”。
   * **鼠标**
     * 右键单击代码，选择“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“用方法替换属性”。

1. 如果对代码预览中的更改感到满意，请按“Enter”或单击菜单中的“修复”，即可提交所做的更改。

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)