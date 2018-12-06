---
title: 如何： 在调用堆栈窗口中的缺少本机框架时跳出托管代码 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Call Stack window, missing native frames
- code, managed code
- native frames
- stepping, out of managed code
- managed code, stepping out of
ms.assetid: 97cdd2a8-02a9-4a06-a5b1-c92b1e431979
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e5c671f93e20da108a9fd1069a0950f52ef00da9
ms.sourcegitcommit: dd839de3aa24ed7cd69f676293648c6c59c6560a
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "52388564"
---
# <a name="how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window"></a>如何：在“调用堆栈”窗口中缺少本机框架时跳出托管代码

如果代码具有在**调用堆栈**窗口中不可见的本机框架，则跳出托管代码可能会产生意外结果。一种解决方法是，使用断点来代替**跳出**。

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[重置设置](../ide/environment-settings.md#reset-settings)。

## <a name="step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-display"></a>当“调用堆栈”显示中缺少本机框架时，跳出托管代码

1.  在本机代码中，调用托管代码的后面设置一个位置断点。

2. 在**调试**菜单上选择**继续**。

     托管调用完成后，执行会在本机代码的断点处停止。

## <a name="see-also"></a>请参阅

- [如何：使用“调用堆栈”窗口](../debugger/how-to-use-the-call-stack-window.md)
