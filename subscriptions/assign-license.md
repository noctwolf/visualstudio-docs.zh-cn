---
title: 将许可证分配给 Visual Studio 订阅 | Microsoft Docs
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.date: 07/16/2018
ms.topic: conceptual
description: 了解管理员如何将许可证分配给订阅者
searchscope: VS Subscription
ms.openlocfilehash: 97962571d8a7c433a5f72af90d9107f9e2b08a9b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946415"
---
# <a name="assign-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>在 Visual Studio 订阅管理员门户中分配许可证

作为 Visual Studio 订阅管理员，可以使用管理员门户为个人用户和用户组分配订阅。

对于用户组，可每次分配一个订阅，也可使用“批量添加”功能快速轻松地上传订阅者列表及其订阅信息。

## <a name="individual-assignments"></a>单项分配

下面介绍如何为新用户分配 Visual Studio 订阅许可证，以便他们可以访问订阅权益。

1. 登录到[管理员门户](https://manage.visualstudio.com)。

2. 要为单个 Visual Studio 订阅者分配许可证，请在表的顶部选择“添加”。
   > [!div class="mx-imgBorder"]
   > ![添加单个订阅者](media/add-single-subscriber.png)

3. 在表单域中输入新订阅者的信息。 如果组织使用 Azure Active Directory，则此字段可充当搜索功能，查找当前目录中的用户，以便从搜索结果中选择正确的用户。 选择用户后，系统会自动填充该用户的名称、登录电子邮件和通知电子邮件。
   > [!div class="mx-imgBorder"]
   > ![添加新通知电子邮件地址](media/add-new-subscriber-notification-email.png)

    如果希望此订阅者在登录 [Visual Studio 订阅门户](https://my.visualstudio.com?wt.mc_id=o~msft~docs)时可以访问软件下载，请务必将“下载设置”部分中的下载切换保持启用状态。 如果选择禁用下载，用户将无法访问软件下载，但仍可访问订阅中包含的所有其他权益。
   > [!div class="mx-imgBorder"]
   > ![下载的访问权限](media/access-to-downloads.png)

    如果想要更改订阅者接收信息的语言，则可以在“通信首选项”部分中进行更改。
   > [!div class="mx-imgBorder"]
   > ![更改要在发送通知电子邮件时使用的语言](media/change-subscriber-communication-preference.png)

    如果要向订阅添加自己的引用说明，则可以在“添加引用”部分执行操作。
   > [!div class="mx-imgBorder"]
   > ![向每个订阅添加自己的引用说明](media/add-subscriber-reference-notes.png)

    完成选择选项和输入订阅者数据后，选择“添加订阅者”弹出窗口底部的“添加”。
   > [!div class="mx-imgBorder"]
   > ![选择“添加”按钮](media/add-button.png)

4. 添加订阅者后，系统会向新订阅者自动发送一封分配电子邮件，为其提供进一步说明。 通过选中订阅者和单击顶部菜单中的“重新发送”按钮，可以随时再次发送分配电子邮件。
   > [!div class="mx-imgBorder"]
   > ![随时向任何用户或多个用户重新发送激活电子邮件](media/resend-subscriber-activation-emails.png)

## <a name="bulk-assignments"></a>批量分配

1. 若要一次添加多个订阅者，请导航到“管理订阅者”选项卡。在顶部功能区，单击“批量添加”。
   > [!div class="mx-imgBorder"]
   > ![添加多个订阅者](media/add-multiple-subscribers.png)

2. 批量分配会使用 Microsoft Excel 模板上传订阅者。 在“上传多个订阅者”对话框中，单击“下载”下载模板。
   > [!div class="mx-imgBorder"]
   > ![下载 Excel 模板以上传多个订阅者](media/download-template-upload-subscribers.png)
   >
   > [!NOTE]
   > 请务必下载本模板的最新版本。 如果使用旧版本，批量上传可能会失败。

3. 在 Excel 电子表格的字段中，填写想要为其分配订阅的个人的信息。 （“引用”是可选字段。）完成后将文件保存在本地。

   为顺利地完成上传，请查看以下最佳做法：

    - 确保所有表单域均不含逗号。
    - 删除表单域前后的空格。
    - 确保用户名在名字和姓氏两部分之间不含额外空格（例如，用户姓名为两部分的“Maggie May”，则应输成“MaggieMay”，因为系统不会删减额外空格）。

4. 返回到 Visual Studio 订阅管理门户。 在“上传多个订阅者”对话框中，单击“浏览”。
   > [!div class="mx-imgBorder"]
   > ![浏览到之前保存的模板以上传多个订阅者](media/bulk-add-browse-saved-template.png)

5. 导航到之前保存的 Excel 文件，然后单击“确定”。
   > [!div class="mx-imgBorder"]
   > ![上传 Excel 模板以上传多个订阅者](media/bulk-upload-subscribers.png)

    将显示上传进度对话框。

    如果模板中存在错误，则无法上传。系统会显示该错误，你可以更正模板，然后再次尝试批量上传。
   > [!div class="mx-imgBorder"]
   > ![如果上传多个订阅者失败，将显示错误消息](media/bulk-add-template-failed.png)

    上传成功后，系统会显示订阅者列表和一条确认消息。
   > [!div class="mx-imgBorder"]
   > ![如果上传多个订阅者成功，将显示确认消息](media/bulk-add-template-success.png)
