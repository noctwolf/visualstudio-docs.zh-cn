---
title: "如何： 添加 Updater 方法 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], updating data
- BDC [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating data
- Business Data Connectivity service [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating entity instances
- BDC [SharePoint development in Visual Studio], updating entity instances
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 506d22358493d7b38a6cdfac6cee9efd97435943
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-an-updater-method"></a>如何：添加 Updater 方法
  你可以使用户能够通过创建更新 SharePoint 外部列表中的业务数据*更新程序*方法。 有关详细信息，请参阅[设计业务数据连接模型](../sharepoint/designing-a-business-data-connectivity-model.md)。  
  
### <a name="to-create-an-updater-method"></a>若要创建 Updater 方法  
  
1.  在 BDC 设计器中，选择实体。  
  
2.  在菜单栏上，选择**视图**，**其他窗口**， **BDC 方法详细信息**。  
  
     “BDC 方法详细信息”窗口将打开。 有关此窗口的详细信息，请参阅[BDC 模型设计工具概述](../sharepoint/bdc-model-design-tools-overview.md)。  
  
3.  在**添加一个方法**列表中，选择**创建 Updater 方法**。  
  
     Visual Studio 将以下元素添加到模型。 在 BDC 方法详细信息窗口中显示这些元素。  
  
    -   名为的方法**更新**。  
  
    -   输入的参数的方法。  
  
    -   参数类型描述符。 默认情况下，Visual Studio 使用你定义的实体类型描述符的 Finder 方法 (例如： 联系人)。  
  
    -   方法实例的方法。  
  
     有关详细信息，请参阅[设计业务数据连接模型](../sharepoint/designing-a-business-data-connectivity-model.md)。  
  
    > [!NOTE]  
    >  如果实体类型的标识符表示不自动生成的数据库表中的字段，设置**预更新程序字段**属性**True**。  
  
4.  在**解决方案资源管理器**，打开实体，已生成的服务代码文件的快捷菜单，然后选择**查看代码**。  
  
     实体服务代码文件将在代码编辑器中打开。 关于该文件的详细信息，请参阅[创建业务数据连接模型](../sharepoint/creating-a-business-data-connectivity-model.md)。  
  
5.  将代码添加到要更新的数据的更新方法。 下面的示例更新 AdventureWorks 示例数据库中联系人为 SQL Server 的信息。  
  
    > [!NOTE]  
    >  值替换`ServerName`字段替换为你的服务器的名称。  
  
     [!code-csharp[SP_BDC#5](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#5)]
     [!code-vb[SP_BDC#5](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#5)]  
  
## <a name="see-also"></a>请参阅  
 [设计业务数据连接模型](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [如何： 添加 Finder 方法](../sharepoint/how-to-add-a-finder-method.md)   
 [如何： 添加特定的 Finder 方法](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [如何： 添加 Creator 方法](../sharepoint/how-to-add-a-creator-method.md)   
 [如何： 添加 Updater 方法](../sharepoint/how-to-add-an-updater-method.md)   
 [如何： 添加 Deleter 方法](../sharepoint/how-to-add-a-deleter-method.md)   
 [BDC 模型设计工具概述](../sharepoint/bdc-model-design-tools-overview.md)   
 [如何： 向方法添加参数](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [如何：定义方法实例](../sharepoint/how-to-define-a-method-instance.md)  
  
  