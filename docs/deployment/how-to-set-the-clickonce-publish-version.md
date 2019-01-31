---
title: 如何：设置 ClickOnce 发布版本 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, setting publish version
- publishing, ClickOnce
- Publish Version property
ms.assetid: 06f15504-6385-40a6-b01d-cd90ca36dc73
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7908bb88e13dff34721b7c6419d0a7f036be68d1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54923579"
---
# <a name="how-to-set-the-clickonce-publish-version"></a>如何：设置 ClickOnce 发布版本
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] `Publish Version`属性确定是否要发布的应用程序视为更新。 每个时间版本递增时，将作为更新发布应用程序。  
  
 `Publish Version`属性可以设置上**发布**页**项目设计器**。  
  
> [!NOTE]
>  将自动递增的项目选项`Publish Version`属性每次发布应用程序; 默认情况下启用此选项。 有关详细信息，请参阅[如何：自动递增 ClickOnce 发布版本](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)。  
  
### <a name="to-change-the-publish-version"></a>若要更改的发布版本  
  
1.  在“解决方案资源管理器” 中选择一个项目，然后在“项目”  菜单上单击“属性” 。  
  
2.  单击“发布”选项卡。  
  
3.  在中**发布版本**字段中，递增**主要**，**次要**，**生成**，或**修订**版本数字。  
  
    > [!NOTE]
    >  应永远不会递减版本号;这样做可能导致不可预知的更新行为。  
  
## <a name="see-also"></a>请参阅  
 [选择 ClickOnce 更新策略](../deployment/choosing-a-clickonce-update-strategy.md)   
 [如何：自动递增 ClickOnce 发布版本](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [发布 ClickOnce 应用程序](../deployment/publishing-clickonce-applications.md)   
 [如何：使用发布向导发布 ClickOnce 应用程序](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)