---
title: 在 Visual Studio 订阅管理员门户中管理管理员权限
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 1/19/2018
Ms.topic: Get-Started-Article
Description: Learn how manage admins & super admins in the Visual Studio Subscriptions Administrator Portal.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 83bf27d5aaa99c2095ad8a1fafd7541df90f316b
ms.sourcegitcommit: a0a49cceb0fdc1465ddf76d131c6575018b628b8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
# <a name="managing-administrator-rights-in-the-visual-studio-subscriptions-administrator-portal"></a>在 Visual Studio 订阅管理员门户中管理管理员权限

## <a name="overview"></a>概述 
Visual Studio 订阅管理员门户 (https://manage.visualstudio.com)) 具有两个管理角色：

超级管理员：首次设置组织时，“主要联系人或通知联系人”在默认情况下会成为超级管理员。 主要联系人或通知联系人可以选择分配其他超级管理员或管理员。 除了管理各个订阅者的订阅，超级管理员还可以添加和删除其他管理员和超级管理员。 如果系统中有两个以上的超级管理员，为了安全起见，超级管理员可以删除最后两个以外的所有超级管理员。 

管理员：管理员可以在超级管理员分配给订阅者的协议中对其进行管理。  他们可以将订阅分配给个人、编辑订阅，并重新分配或删除它们。   （管理员由超级管理员指定。）  

## <a name="adding-an-administrator-with-super-admin-rights"></a>通过超级管理员权限添加管理员：

1. 使用已具有超级管理员权限的帐户登录到 Visual Studio 订阅[管理员门户](https://manage.visualstudio.com)。

2. 单击页面顶部的“管理管理员”选项卡。 （仅超级管理员有权访问此选项卡。没有超级管理员权限的管理员使用“管理订阅者”选项卡来管理各个订阅者。）

3. 单击“添加”创建新的管理员。 

4. 在“添加管理员”弹出窗口中填写所有请求的详细信息。
  - 如果组织已经注册 Azure Active Directory (AAD)，请先在“名称”字段中键入名称，并在下拉列表上选择正确项。 对于新用户，请键入完整名称，并忽略“未找到任何标识”通知。
  - 一旦识别正确用户，将自动填充登录电子邮件地址字段。 键入新管理员的电子邮件地址（如果尚未提供）。

5. 通过单击“协议”下的下拉列表，选择想要新管理员管理的“PCN”。 如果载入的 PCN 在其下具有多个协议，则可以为管理员提供对任何或所有协议的访问权限。 

有关协议的详细信息：当只有一个协议可用时，“协议”下的下拉列表功能将被禁用。  当你配置的用户被授予超级管理员权限时，会自动选中所有协议。

6. 单击“超级管理员”框，可为此管理员启用超级管理员权限。  

7. 要添加此管理员，请单击“添加”。

添加管理员时收到潜在错误：尝试添加管理员时，某些用户可能会收到错误消息。 如果正在添加的超级管理员电子邮件地址未在公司的 AAD 中列出，则可能会发生这种情况。 若要完成添加新管理员，只需忽略该错误，然后再次单击“添加”即可。 

8. 一旦创建超级管理员，他们即会出现在管理员列表中，且其帐户标有绿色复选标记，以指示其超级管理员状态。 

### <a name="optional--add-a-different-notification-email"></a>可选：添加不同的通知电子邮件。
如果组织使用不同地址/帐户用于接收电子邮件，此时可以选择输入“通信”地址。 选择“添加用于接收通信的不同通知电子邮件”。 

示例：当 Rene 使用其公司凭据登录时，续订将使用 rene@contoso.com。  但是，Rene 的公司仅使用该地址来管理目录访问权限。  在发送和接收电子邮件时，Rene 使用了 rene.collado@contoso.com，因此，他的超级管理员已输入第二个地址，以确保他收到欢迎邮件。  如果你的公司未以此方式配置，则只需输入登录电子邮件地址即可。

## <a name="adding-an-administrator-without-super-admin-rights"></a>在没有超级管理员权限的情况下添加管理员：

在没有超级管理员权限的情况下，若要添加管理员，应遵循上文所述的相同过程，但还要考虑以下几个方面：
-  在没有超级管理员权限的情况下添加管理员时，无需添加其他电子邮件地址，且超级管理员复选框保留为空。
-  不具备超级管理员权限的用户在其“管理管理员”下的配置文件配置项中，不会收到绿色复选框图标。
