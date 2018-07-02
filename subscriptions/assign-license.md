---
title: 将许可证分配给 Visual Studio 订阅 | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 10/03/2017
ms.topic: Get-Started-Article
description: 了解管理员如何将许可证分配给订阅者
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 4325921bbaa75e0fb8a8a16947c45901b6f01649
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34477374"
---
# <a name="assigning-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>在 Visual Studio 订阅管理员门户中分配许可证

作为 Visual Studio 订阅管理员，可以使用 Visual Studio 订阅管理员门户为个人用户分配订阅。  
可以每次分配一个订阅，也可以使用“批量添加”功能快速轻松地上传订阅者列表及其订阅信息。 

## <a name="assigning-a-single-user"></a>分配给单个用户
如果拥有 Visual Studio 订阅的可用许可证，可以将这些许可证分配给新用户，让他们能够享受订阅权益。 
1.  登录到[管理员门户](https://manage.visualstudio.com)

2.  要分配给单个 Visual Studio 订阅者，请在表的顶部单击“添加”。

    <img alt="Add subscriber" src="_img\assign-license-add\assign-license-add.png" style="border: 1px solid #CCCCCC" />

3.  在表单域中输入新订阅者的信息。 如果组织使用 Azure Active Directory，则此字段可充当搜索功能，查找当前目录中的用户，以便从搜索结果中选择正确的用户。 选择用户后，系统会自动填充该用户的名称、登录电子邮件和通知电子邮件，如下所示。 

    如果贵组织不使用 Azure Active Directory (Azure AD)，而是使用与登录电子邮件不同的电子邮件地址来接收电子邮件，则可以在此处输入该电子邮件地址。 选择标记为“添加其他电子邮件地址来接收通信”的超链接。 

    **下载的访问权限：**  
    如果希望此订阅者在登录 [Visual Studio 订阅门户](https://my.visualstudio.com?wt.mc_id=o~msft~docs)时可以访问软件下载，请务必将下载切换保持启用状态。 如果选择禁用下载，用户将无法访问软件下载，但仍可访问订阅中包含的所有其他权益。 
    
    为此订阅者选择选项后，单击“添加”。

    <img alt="Enter subscriber information" src="_img\assign-license-add\add-subscriber-1.png" style="border: 1px solid #CCCCCC" />
    <img alt="Enter subscriber information" src="_img\assign-license-add\add-subscriber-2.png" style="border: 1px solid #CCCCCC" />

4.  添加订阅者后，系统会向新订阅者自动发送一封分配电子邮件，为其提供进一步说明。 通过选中订阅者和单击顶部菜单中的“重新发送”按钮，可以随时再次发送分配电子邮件。

    <img alt="Subscriber added" src="_img\assign-license-add\add-subscriber-complete.png" style="border: 1px solid #CCCCCC" />

## <a name="bulk-assignments"></a>批量分配
1.  若要一次添加多个订阅者，请导航到“管理订阅者”选项卡。在顶部功能区，单击“批量添加”。 

    <img alt="Bulk add" src="_img\assign-license-add\bulk-assign-add.png" style="border: 1px solid #CCCCCC" />

2. 批量分配会使用 Microsoft Excel 模板上传订阅者。 在“上传多个订阅者”对话框中，单击“下载”下载模板。 请务必下载本模板的最新版本。 如果使用旧版本，批量上传可能会失败。

    <img alt="Upload multiple subscribers" src="_img\assign-license-add\bulk-assign-upload.png" style="border: 1px solid #CCCCCC" />

3.  在 Excel 电子表格的字段中，填写想要为其分配订阅的个人的信息。 引用是可选字段。 如果模板任何部分的填写内容出错，系统会显示描述该问题的错误消息。 完成后在本地保存文件。
为顺利地完成上传，请查看以下最佳做法：
    - 确保所有表单域均不含逗号。
    - 删除用户名等表单域前后的空格。
    - 确保用户名在名字和姓氏两部分之间不含额外空格（例如，“Maggie May”不能输成“Maggie  May”，因为系统不会删减额外空格）。
    <img alt="Bulk add template" src="_img\assign-license-add\bulk-template.png" style="border: 1px solid #CCCCCC" />

4.  返回 Visual Studio 订阅管理门户，在“上传多个订阅者”对话框中，单击“浏览”。 导航到之前保存的 Excel 文件，然后单击“确定”。 屏幕上随即显示上传进度。 

    <img alt="Bulk add upload" src="_img\assign-license-add\bulk-assign-upload-2.png" style="border: 1px solid #CCCCCC" />

如果模板中存在错误，则无法上传。系统会显示该错误，你可以更正模板，然后再次尝试批量上传。
    <img alt="Upload fail" src="_img\assign-license-add\bulk-assign-upload-fail.png" style="border: 1px solid #CCCCCC" />

上传成功后，系统会显示订阅者列表和一条确认消息。

   <img alt="Upload complete" src="_img\assign-license-add\bulk-assign-upload-complete.png" style="border: 1px solid #CCCCCC" />