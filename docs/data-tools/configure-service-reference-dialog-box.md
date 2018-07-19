---
title: “配置服务引用”对话框
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msvse_wcf.dlg.ConfigureServiceReference
helpviewer_keywords:
- WCF services, Configure Service Reference dialog box
- service references [Visual Studio], configuring behavior
- Configure Service Reference dialog box
ms.assetid: 25e4c36b-2db6-4e71-9010-b7068255d09d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 93d39aedc04cbdaebc35c892a8393ca394f44898
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281061"
---
# <a name="configure-service-reference-dialog-box"></a>“配置服务引用”对话框

**配置服务引用**对话框中，您可以配置 Windows Communication Foundation (WCF) 服务的行为。

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md)。

访问**配置服务引用**对话框中，右击的服务中引用**解决方案资源管理器**，然后选择**配置服务引用**。 此外可以通过单击访问对话框的**高级**按钮**添加服务引用对话框**。

## <a name="task-list"></a>任务列表

- 若要更改托管 WCF 服务的地址，请输入中的新地址**地址**字段。

- 若要更改 WCF 客户端中的类的访问级别，请选择中的访问级别关键字**访问生成的类的级别**列表。

- 若要以异步方式调用 WCF 服务的方法，请选择**生成异步操作**复选框。

- 若要在 WCF 客户端生成消息协定类型，请选择**始终生成消息约定**复选框。

- 若要为 WCF 客户端指定列表或字典集合类型，选择从类型**集合类型**并**字典集合类型**列出。

- 若要禁用类型共享，请清除**重新使用引用的程序集的类型**复选框。 若要启用类型共享引用的程序集的子集，请选择**重新使用引用的程序集的类型**复选框，选中**重新使用的指定被引用程序集中的类型**，并选择所需中的引用**引用的程序集列表**。

## <a name="uielement-list"></a>UIElement 列表

 **地址**

 更新服务引用在其中查找服务的 Web 地址。 例如，在开发期间，服务可能是托管在开发服务器上，然后更高版本移到生产服务器，因而需要进行地址更改。

> [!NOTE]
> 地址元素不可用**配置服务引用**从显示对话框**添加服务引用对话框**。

 **生成的类的访问级别**

 确定 WCF 客户端类的代码访问级别。

> [!NOTE]
> 对于网站项目，该选项将始终设置为 `Public`，并且无法更改。 有关详细信息，请参阅[服务引用疑难解答](../data-tools/troubleshooting-service-references.md)。

 **生成异步操作**

 确定是否以同步方式调用 WCF 服务的方法 （默认值） 或以异步方式。

 **生成基于任务的操作**

 编写异步代码时，此选项允许您充分利用的任务并行库 (TPL) 引入的.NET 4。 请参阅[任务并行库 (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl)。

 **始终生成消息约定**

 确定是否将消息协定类型生成 WCF 客户端。 有关消息约定的详细信息，请参阅[使用消息协定](/dotnet/framework/wcf/feature-details/using-message-contracts)。

 **集合类型**

 为 WCF 客户端指定列表集合类型。 默认类型为 <xref:System.Array>。

 **字典集合类型**

 为 WCF 客户端指定字典集合类型。 默认类型为 <xref:System.Collections.Generic.Dictionary%602>。

 **重新使用引用的程序集的类型**

 确定 WCF 客户端是否尝试重复使用什么中引用的程序集，而不是生成新类型添加或更新服务时已存在。 默认情况下，此选项处于选中状态。

 **重新使用所有引用的程序集的类型**

 选择中的所有类型时**引用的程序集列表**如有可能重复使用。 默认情况下，该选项是选中的。

 **重新使用的指定被引用程序集中的类型**

 选择中的所选的类型时**引用的程序集列表**会重复使用。

 **引用的程序集列表**

 包含一个列表，此列表针对项目或网站列出了引用的程序集。 当选择**重新使用的指定被引用程序集中的类型**，可以选中或清除各个程序集。

 **添加 Web 引用**

 显示**添加 Web 引用**对话框。

> [!NOTE]
> 此选项应仅用于面向 2.0 版的项目[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]。

> [!NOTE]
> **添加 Web 引用**按钮才可用**配置服务引用**对话框中显示从**添加服务引用对话框**。

## <a name="see-also"></a>请参阅

- [如何： 添加对 web 服务的引用](how-to-add-update-or-remove-a-wcf-data-service-reference.md)
- [Windows Communication Foundation 服务和 WCF 数据服务](../data-tools/configure-service-reference-dialog-box.md)