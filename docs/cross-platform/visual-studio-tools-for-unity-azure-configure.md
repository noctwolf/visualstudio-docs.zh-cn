---
title: "Visual Studio Tools for Unity Azure 演练配置 |Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: BAE62C27-CA7A-4466-8738-3DB880221CE1
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 25424ea06c01224bb1b35f783be82a857b991adf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="configure-easy-tables-in-azure"></a>在 Azure 中配置简易表

建议表是 [Azure 移动应用](https://azure.microsoft.com/services/app-service/mobile/)的一个功能，通过它可以直接在 Azure 门户 GUI 中设置和管理 SQL 表。 Azure 移动应用支持许多功能，但是此示例的范围仅限于从 Unity 项目读取和写入存储在 Azure 移动应用后端中的数据。

## <a name="create-a-new-azure-mobile-app"></a>创建新的 Azure 移动应用

登录到 [Azure 门户](https://ms.portal.azure.com)。 如果你没有 Azure 订阅，则[免费试用版](https://azure.microsoft.com/en-us/free/)或 [Visual Studio Dev Essentials](https://www.visualstudio.com/dev-essentials/) 中包含的点数已足以完成本演练。

**处于门户中之后：**

1. 选择“新建”>“Web + 移动”>“移动应用”>“创建”。

  ![创建新的移动应用](media/vstu_azure-configure-easy-tables-image1.png)

2. 配置新的移动应用：

  * **应用名称**。 这会生成用于连接到 Azure 移动应用后端的 URL。 必须选择唯一名称（由绿色复选标记进行指示）。

  * **订阅**。 选择新的移动应用将用于计费的订阅。

  * **资源组**。 通过资源组可以更轻松地管理相关资源。 默认情况下，Azure 会创建名称与新应用相同的新资源组。 默认设置适用于本演练。

  *  **应用服务计划/位置**。 服务计划指示 Azure 用于承载新移动应用的资源的计算能力、位置和成本。 默认情况下，Azure 会创建具有一些默认设置的新服务计划。 这是用于本演练的最简单选项。 但是，可以使用此菜单可以自定义新服务计划的定价层或地理位置。 此外，可以在部署服务计划之后修改其设置。

  ![创建新的移动应用](media/vstu_azure-configure-easy-tables-image2.png)

3. 选择“创建”并等待 Azure 几分钟以部署新资源。 完成部署后，你会在 Azure 门户中看到通知。

## <a name="add-a-new-data-connection"></a>添加新数据连接

4. 完成部署后，单击“所有资源”按钮，然后选择新创建的移动应用。

  ![选择新的移动应用](media/vstu_azure-configure-easy-tables-image3.png)

5. 在新打开的边栏选项卡中，向下滚动左侧菜单，然后单击在“移动”标题下列出的“简易表”按钮。

  ![选择“简易表”](media/vstu_azure-configure-easy-tables-image4.png)

6. 单击沿“简易表”边栏选项卡顶部显示的蓝色“需要配置简易表/简易 API”通知。

  ![单击配置简易表通知](media/vstu_azure-configure-easy-tables-image5.png)

7. 单击显示“需要数据库才能使用简易表。单击此处创建一个”的通知。

  ![单击创建数据库通知](media/vstu_azure-configure-easy-tables-image6.png)

8. 在“数据连接”边栏选项卡上，单击“添加”按钮。

  ![单击“添加”按钮](media/vstu_azure-configure-easy-tables-image7.png)

9. 在“添加数据连接”边栏选项卡上，选择“SQL 数据库”。

  ![选择“SQL 数据库”](media/vstu_azure-configure-easy-tables-image8.png)

10. 一个边栏选项卡随即打开，用于配置新 SQL 数据库和 SQL 服务器：

  * **名称**。 为数据库输入名称。

  * **目标服务器**。 单击“目标服务器”以打开“新服务器”边栏选项卡。

      * **服务器名称**。 为服务器输入名称。

      * **服务器管理员登录名和密码**。 为服务器管理员创建用户名和密码。

      * **位置**。 选择服务器的附近位置。

      * 确保“允许 Azure 服务访问服务器”复选框保持选中状态。

      * 单击“选择”以完成服务器配置。

    * **定价层**。 对于本演练保留默认设置。 这可以在以后进行修改。

    * **排序规则**。 保留默认设置。

    * 单击“选择”以完成数据库配置。

    ![配置 SQL 服务器和数据库](media/vstu_azure-configure-easy-tables-image9.png)

11. 返回“添加数据连接”边栏选项卡，单击“连接字符串”。 当“连接字符串”边栏选项卡出现时，保留默认设置，然后单击“确定”。

  ![单击“连接字符串”](media/vstu_azure-configure-easy-tables-image9.1.png)

12. 返回“添加数据连接”边栏选项卡，文本“MS_TableConnectionString”应不再以斜体显示。 单击“确定”并等待 Azure 几分钟以创建新数据连接。 该过程完成后，会出现一个通知。

  ![单击“确定”](media/vstu_azure-configure-easy-tables-image9.2.png)

## <a name="complete-the-easy-table-initialization"></a>完成简易表初始化

13. 成功创建新数据连接之后，单击“所有资源”按钮，然后再次导航回到移动应用。 请务必完成此步骤以刷新简易表配置通知。

14. 向下滚动并选择“简易表”，然后再次选择蓝色“需要配置简易表/简易 API”。

  ![单击简易表通知](media/vstu_azure-configure-easy-tables-image5.png)

15. 这次出现的边栏选项卡应在“1”标题下显示“已经有数据连接”。 在“2”标题下，单击显示“我已了解此操作会覆盖所有站点内容”的复选框。 现在单击“初始化应用”并等待 Azure 几分钟以完成初始化过程。 该过程完成后，会出现一个新通知。

  ![单击“初始化应用”](media/vstu_azure-configure-easy-tables-image10.png)

## <a name="next-step"></a>下一步

* [创建简易表](visual-studio-tools-for-unity-azure-setup.md)
