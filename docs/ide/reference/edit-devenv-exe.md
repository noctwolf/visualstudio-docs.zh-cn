---
title: -Edit (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- Edit Devenv switch
- Devenv, /Edit switch
- /Edit Devenv switch
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 26433d62a68b28450a56eee1282376733acfe55c
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55911905"
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)

在现有 Visual Studio 实例中打开指定文件。

## <a name="syntax"></a>语法

```shell
devenv /Edit [File1[ FileN]...]
```

## <a name="arguments"></a>自变量

- File1

  可选。 要在现有 Visual Studio 实例中打开的文件。 如果没有 Visual Studio 实例，便会新建包含简化窗口布局的实例，且工具会在新实例中打开 File1。

- FileN

  可选。 要在现有 Visual Studio 实例中打开的一个或多个其他文件。

## <a name="remarks"></a>备注

如果文件未指定，现有 Visual Studio 实例便会接收焦点。 如果文件未指定且没有 Visual Studio 实例，工具会创建包含简化窗口布局的实例。

如果现有 Visual Studio 实例处于模式状态，那么文件会在 Visual Studio 退出模式状态时在现有实例中打开。 例如，当[“选项”对话框](../../ide/reference/options-dialog-box-visual-studio.md)打开时，可能会出现这种情况。

## <a name="example"></a>示例

第一个示例在现有 Visual Studio 实例中打开文件 `MyFile.cs`。 如果没有 Visual Studio 实例，工具在新实例中打开文件。 第二个示例也是相似的，区别在于它打开三个文件，而不是只打开一个文件。

```shell
devenv /edit MyFile.cs

devenv /edit MyFile1.cs MyFile2.cs MyFile3.cs
```

## <a name="see-also"></a>请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)