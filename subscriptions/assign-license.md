---
Title: Assign licenses to Visual Studio Subscriptions | Microsoft Docs
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 10/3/2017
Ms.topic: Get-Started-Article
Description: Learn how administrators can assign licenses to subscribers
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: b82f02b968398d0a8d1ce4872ce00e8447a2ae4d
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2018
---
# <a name="assigning-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>在 Visual Studio 订阅管理员门户中分配许可证

## <a name="assigning-a-single-user"></a>分配给单个用户
如果拥有 Visual Studio 订阅的可用许可证，可以将这些许可证分配给新用户，让他们能够享受订阅权益。 
1.  要分配给单个 Visual Studio 订阅者，请在表的顶部单击“添加”。

    ![添加订阅者](_img\assign-license-add\assign-license-add.png)

2.  在表单字段中输入新订阅者的信息。 如果组织使用 Azure Active Directory，则此字段可充当搜索功能，查找当前目录中的用户，以便从搜索结果中选择正确的用户。 选择用户后，系统会自动填充该用户的名称、登录电子邮件和通知电子邮件，如下所示。 

如果组织用于接收和用于登录的电子邮件不同，可选择在此处输入用于接收的电子邮件。 选择指示“使用不同于登录电子邮件的电子邮件进行通信？”的超链接。 

如果希望此订阅者在登录 [Visual Studio 订阅门户](https:/my.visualstudio.com?wt.mc_id=o~msft~docs)时可以访问软件下载，请务必选中“下载”框。 如果选择取消选中此框，用户会无法访问软件下载，但仍可使用订阅中包含的所有其他权益。 完成后，单击“添加”。

   ![输入订阅者信息](_img\assign-license-add\add-subscriber-1.png)

   ![输入订阅者信息](_img\assign-license-add\add-subscriber-2.png)

3.  添加订阅者后，系统会向新订阅者自动发送一封分配电子邮件，为其提供进一步说明。 通过选中订阅者和单击顶部菜单中的“重新发送”按钮，可以随时再次发送分配电子邮件。

    ![订阅者已添加](_img\assign-license-add\add-subscriber-complete.png)

## <a name="bulk-assignments"></a>批量分配
1.  要一次添加多个订阅者，请导航到“订阅者”选项卡。在顶部功能区，单击“批量添加”。 

    ![批量添加](_img\assign-license-add\bulk-assign-add.png)

2. 批量分配会使用 Microsoft Excel 模板上传订阅者。 在“上传多个订阅者”对话框中，单击“下载”下载模板。 请务必下载本模板的最新版本。 如果使用旧版本，批量上传可能会失败。

    ![上传多个订阅者](_img\assign-license-add\bulk-assign-upload.png)

3.  在 Excel 电子表格的字段中，填写想要为其分配订阅的个人的信息。 引用是可选字段。 如果模板任何部分的填写内容出错，系统会显示描述该问题的错误消息。 完成后将该文件保存在硬盘驱动器上。
为顺利地完成上传，请查看以下最佳做法：
    - 确保所有表单域均不含逗号。
    - 删除用户名等表单域前后的空格。
    - 确保用户名在名字和姓氏两部分之间不含额外空格（例如，“Maggie May”不能输成“Maggie  May”，因为系统不会删减额外空格）

   ![批量添加模板](_img\assign-license-add\bulk-template.png)

4.  返回 Visual Studio 订阅管理门户，在“上传多个订阅者”对话框中，单击“浏览”。 导航到之前保存的 Excel 文件，然后单击“确定”。 屏幕上随即显示上传进度。 

    ![批量添加上传](_img\assign-license-add\bulk-assign-upload-2.png)

如果模板中存在错误，则无法上传。系统会显示该错误，你可以更正模板，然后再次尝试批量上传。

   ![上传失败](_img\assign-license-add\bulk-assign-upload-fail.png)

上传成功后，系统会显示订阅者列表和一条确认消息。

   ![上传完成](_img\assign-license-add\bulk-assign-upload-complete.png)