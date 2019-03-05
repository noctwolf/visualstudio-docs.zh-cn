---
title: 支持阿拉伯语和希伯来语的应用
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Hebrew character display, creating applications
- bidirectional language support, about bidirectional language support
- Arabic language, creating applications
ms.assetid: b56f9795-ed8d-4452-9d49-8ca0b0145d86
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 99df6eddcdd6f02e4cce8410762d3c0b9f00f29a
ms.sourcegitcommit: 845442e2b515c3ca1e4e47b46cc1cef4df4f08d8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "56450316"
---
# <a name="create-applications-in-bidirectional-languages"></a>以双向语言创建应用程序

通过使用 Visual Studio，可以创建能正确显示从右向左书写的语言（包括阿拉伯语和希伯来语）文本的应用程序。 对于某些功能，只需设置属性即可。 而在其他一些情况下，必须通过代码来实现功能。

> [!NOTE]
> 要输入和显示双向语言，必须使用已配置相应语言的 Windows 版本。 可以是安装了适当语言包的英文版 Windows，或者是已相应本地化的 Windows 版本。

## <a name="types-of-applications-that-support-bidirectional-languages"></a>支持双向语言的应用程序类型

-  Windows 应用

   你可以创建完全双向的应用程序，包括支持双向文本、从右到左的读取顺序以及镜像（用于翻转窗口、菜单、对话框等的布局）。 除镜像外，这些功能都作为默认功能或属性设置提供。 某些功能（例如消息框）本身就支持镜像。 但在其他情况下，必须通过代码实现镜像。 有关详细信息，请参阅 [Windows 窗体应用程序的双向支持](/dotnet/framework/winforms/advanced/bidirectional-support-for-windows-forms-applications)。

-  Web 应用

   Web 服务支持发送和接收 UTF-8 及 Unicode 文本，从而使它们适用于涉及双向语言的应用程序。 Web 客户端应用程序需借助浏览器的用户界面，因此，Web 应用程序中的双向支持程度取决于用户的浏览器对这些双向功能的支持程度。 在 Visual Studio 中，创建的应用程序可以支持阿拉伯语或希伯来语文本、从右向左读取顺序、文件编码和本地区域性设置。 有关详细信息，请参阅 [ASP.NET Web 应用程序的双向支持](https://msdn.microsoft.com/Library/5576f9b1-9b86-41ef-8354-092d366bcd03)。

控制台应用不包括对双向语言的文本支持。 这是 Windows 与控制台应用程序搭配使用方式的结果。

## <a name="fully-supported-features"></a>完全受支持的功能

在 Visual Studio 中，可在设计时按如下方式使用双向语言：

- **文本输入**

   Visual Studio 支持 Unicode，因此，如果系统设置了适当的区域设置和输入语言，则可以用阿拉伯语或希伯来语输入文本。 （阿拉伯语支持包括 Kashida 和音调符号。）

- **对象名**

   可使用双向语言向解决方案、项目、文件、文件夹等分配名称。 在代码中，可针对变量名、类名、对象名、特性名、元数据名和其他元素名使用双向语言。

- **文件编码**

   可使用特定语言的编码或 Unicode 编码保存和打开文件。 有关详细信息，请参阅[如何：保存和打开带有编码的文件](../ide/how-to-save-and-open-files-with-encoding.md)。

## <a name="features-with-limited-support"></a>不完全支持的功能

### <a name="right-to-left-reading-order"></a>从右到左的读取顺序

默认情况下，Visual Studio 中使用的文本输入控件使用的是从右到左的读取顺序。 大多数情况可以使用标准 Window 手势来切换读取顺序。 例如，可以按“Ctrl+右 Shift”组合键，将“属性”窗口切换为支持按从右到左的顺序读取属性值。 但是，Visual Studio 中并非所有情况都支持从右到左的读取顺序：

- Visual Studio 对话框中的复选框、下拉列表和其他控件始终使用从左向右的读取顺序。

- 代码编辑器（和文本编辑器）不支持从右到左的读取顺序。 可以用双向语言输入文本，但读取顺序总是从左到右。

## <a name="arabic-or-hebrew-object-names"></a>阿拉伯语或希伯来语对象名

可以使用阿拉伯语或希伯来语文本给文件夹、变量或其他对象指定名称。 使用阿拉伯语时，可使用包括 Kashida 和音调符号在内的任何阿拉伯语字符。

可以使用阿拉伯语或希伯来语给下列元素命名，并且在 Visual Studio 中会得到正确处理：

- 解决方案名、项目名和文件名，包括项目路径中所含的任何文件夹。 解决方案资源管理器会正确显示解决方案名和元素名。

- 文件内容。 可使用 Unicode 编码或选定的代码页来打开或保存文件。

    > [!NOTE]
    > 代码编辑器不支持从右到左的读取顺序。

- 数据元素。 服务器资源管理器将正确显示这些元素，并允许对其进行编辑。

- 复制到 Windows 剪贴板上的元素。

- 特性和元数据。

- 属性值。 可在“属性”窗口中使用阿拉伯语或希伯来语文本。 可在此窗口使用标准的 Windows 击键（“Ctrl+右 Shift”组合键用于从右到左读取，“Ctrl+左 Shift”组合键用于从左到右读取）选择从右到左或从左到右读取顺序。

- 代码和文本。 在代码编辑器中，可使用阿拉伯语或希伯来语命名类、函数、变量、属性、字符串文本、特性等。 但是，编辑器不支持从右向左的读取顺序；文本总是从左边开始。

    > [!TIP]
    > 应将字符串文本放在资源文件中，而不是将其硬编码到程序中。 有关详细信息，请参阅[桌面应用中的资源 (.NET Framework)](/dotnet/framework/resources/index)。

    > [!NOTE]
    > 用阿拉伯语或希伯来语命名的对象的引用方式必须保持一致。 例如，如果使用 Kashida 命名阿拉伯语变量，则引用该变量时必须总是使用 Kashida，否则会产生错误。

- 代码注释。 可使用阿拉伯语或希伯来语创建注释。 还可在注释生成器工具中使用这些语言。