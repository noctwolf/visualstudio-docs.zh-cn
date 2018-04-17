---
title: 如何： 向 Finder 方法中添加筛选器描述符 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], filter descriptors
- Business Data Connectivity service [SharePoint development in Visual Studio], add a filter
- BDC [SharePoint development in Visual Studio], add a filter
- BDC [SharePoint development in Visual Studio], filter descriptors
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 185876ec788bc3fcba917df77a7044a395bc8375
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-a-filter-descriptor-to-a-finder-method"></a>如何：向 Finder 方法中添加筛选器描述符
  筛选器描述符启用模型的使用者执行之前，将值传递给方法。 有关详细信息，请参阅[设计业务数据连接模型](../sharepoint/designing-a-business-data-connectivity-model.md)。  
  
 一个常见方案是在 SharePoint 中的用户想要检索的外部内容类型与某个条件匹配的实例。 可以通过将筛选器描述符添加到 Finder 方法支持此方案。  
  
### <a name="to-add-a-filter-descriptor-to-a-finder-method"></a>若要向 Finder 方法中添加筛选器描述符  
  
1.  在**BDC 方法详细信息**窗口中，展开的 Finder 方法节点，展开**参数**节点，然后添加输入的参数。 有关详细信息，请参阅[如何： 向方法添加参数](../sharepoint/how-to-add-a-parameter-to-a-method.md)。  
  
2.  在**方法详细信息**窗口中，选择参数的类型描述符。  
  
3.  在菜单栏上，选择**视图**，**属性窗口**。  
  
4.  在**属性**窗口中，设置**类型名称**适合于筛选器的数据类型的属性。  
  
     例如，筛选器可能会使用订单日期来限制由该方法返回的销售订单数。 若要支持该筛选器，**类型名称**类型描述符的属性必须设置为**System.DateTime**。  
  
5.  在**方法详细信息**窗口中，展开**筛选器描述符**节点。  
  
6.  在**添加筛选器描述符**列表中，选择**创建筛选器描述符**。  
  
     下方会显示一个新的筛选器描述符**筛选器描述符**节点。  
  
7.  在菜单栏上，选择**视图**，**属性窗口**。  
  
8.  在**属性**窗口中，选择**类型**属性。  
  
9. 在列表中为显示**类型**属性，选择所需的筛选模式。  
  
     例如，若要创建一个使用订单日期来限制在 Finder 方法中返回的销售订单数筛选器，选择**比较**。 比较筛选器确保 finder 方法返回满足特定条件的实例。 有关每个筛选模式的详细信息，请参阅[的筛选器支持的类型 BDC](http://go.microsoft.com/fwlink/?LinkId=169287)。  
  
10. 在**属性**窗口中，选择**关联的类型描述符**属性。  
  
11. 在列表中为显示**关联的类型描述符**属性，选择你在此过程前面创建的类型描述符。 这将筛选器与 Finder 方法的输入参数。  
  
12. 将代码添加到返回数据的 Finder 方法。 为 select 查询中的条件，可以使用输入的参数。  
  
     下面的示例返回具有指定的订单日期的销售订单。  
  
    > [!NOTE]  
    >  值替换`ServerName`字段替换为你的服务器的名称。  
  
     [!code-csharp[SP_BDC#11](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/salesorderservice.cs#11)]
     [!code-vb[SP_BDC#11](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/salesorderservice.vb#11)]  
  
## <a name="see-also"></a>另请参阅  
 [如何： 添加 Finder 方法](../sharepoint/how-to-add-a-finder-method.md)   
 [如何： 添加特定的 Finder 方法](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [如何： 向方法添加参数](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [如何： 定义参数的类型描述符](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [设计业务数据连接模型](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [将业务数据集成到 SharePoint 中](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  