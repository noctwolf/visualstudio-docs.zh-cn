---
title: 如何：定义方法实例 |Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method
- Business Data Connectivity service [SharePoint development in Visual Studio], method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2f879f8367ad1b992300c9e5b1c8a2887e89205b
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56608002"
---
# <a name="how-to-define-a-method-instance"></a>如何：定义方法实例
  在模型中，必须定义至少一个方法实例的每个方法。

 使用添加方法实例**BDC 方法详细信息**窗口。 添加方法实例，请在 Visual Studio 添加`<MethodInstance>`到你的项目中的模型文件的 XML 元素。 有关属性的详细信息`<MethodInstance>`元素，请参阅[MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282)。

### <a name="to-define-a-method-instance"></a>若要定义方法实例

1.  在中**BDC 方法详细信息**窗口中，展开一种方法，该节点，然后展开**实例**节点。

2.  在中**添加方法实例**列表中，选择**创建 Finder 实例**。

     下面将显示一个新的方法实例**实例**节点。

3.  在菜单栏上依次选择**视图** > **属性窗口**。

4.  在中**属性**窗口中，设置方法实例的属性。 有关每个属性的详细信息，请参阅[MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282)。

## <a name="see-also"></a>请参阅
- [BDC 模型设计工具概述](../sharepoint/bdc-model-design-tools-overview.md)
- [如何：向模型添加实体](../sharepoint/how-to-add-an-entity-to-a-model.md)
- [如何：将参数添加到方法](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [如何：定义参数的类型描述符](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)
- [设计业务数据连接模型](../sharepoint/designing-a-business-data-connectivity-model.md)
