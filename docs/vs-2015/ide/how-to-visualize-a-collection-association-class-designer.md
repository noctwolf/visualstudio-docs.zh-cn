---
title: 如何：可视化集合关联（类设计器） | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.classdesigner.collectionassociationline
- vs.classdesigner.ShowAssociationException
helpviewer_keywords:
- collection associations
- collections, collection associations
- Class Designer [Visual Studio], collection associations
ms.assetid: 54e39838-2fc9-4dc2-85b6-7e88a743108e
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 42cf379e9cfb2d8a84412a534eb13702febc945a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482074"
---
# <a name="how-to-visualize-a-collection-association-class-designer"></a>如何：可视化集合关联（类设计器）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 可视化集合关联 （类设计器）](https://docs.microsoft.com/visualstudio/ide/how-to-visualize-a-collection-association-class-designer)。  
  
属于其他类型的集合的属性和字段可在类图上作为集合关联显示。 普通关联可将字段或属性显示为行，此行将拥有的类链接到字段的类型，与此不同，集合关联作为行显示，此行将拥有的类链接到已收集的类型。  
  
### <a name="to-create-a-collection-association"></a>创建集合联合  
  
1.  在代码中，创建一个属性或字段，其本身属于强类型集合。  
  
2.  在类图中扩展类，以便显示属性和字段。  
  
3.  在类中，右键单击该字段或属性，然后选择“显示为集合关联”。  
  
     此属性或字段将显示为链接到已收集类型的关联行。  
  
## <a name="see-also"></a>请参阅  
 [如何：创建类型之间的关联（类设计器）](../ide/how-to-create-associations-between-types-class-designer.md)   
 [设计类和类型（类设计器）](../ide/designing-classes-and-types-class-designer.md)   
 [查看类型和关系（类设计器）](../ide/viewing-types-and-relationships-class-designer.md)



