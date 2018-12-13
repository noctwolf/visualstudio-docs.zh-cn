---
title: 如何：在应用 Visual Basic 开发人员设置后管理生成配置 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio, building with Visual Basic settings
- MSBuild, debug build
- advanced build configurations
- building with Visual Basic developer settings
- debug builds
- MSBuild, release build
- release builds
ms.assetid: eaea6e0b-6c61-4869-8d63-d372c745a23c
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b191b5d4223d32e4d620c779f5813c0db651a6cc
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49300555"
---
# <a name="how-to-manage-build-configurations-with-visual-basic-developer-settings-applied"></a>如何：在应用 Visual Basic 开发人员设置后管理生成配置
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

默认情况下，应用 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 开发人员设置后，所有高级生成配置选项都将隐藏。 本主题说明如何手动启用这些设置。  
  
## <a name="enabling-advanced-build-configurations"></a>启用高级生成配置  
 默认情况下，[!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 开发人员设置将隐藏用于打开“Configuration Manager”对话框以及[项目设计器中](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)的“配置”和“平台”列表的选项。  
  
#### <a name="to-enable-advanced-build-configurations"></a>启用高级生成配置  
  
1.  在 **“工具”** 菜单上，单击 **“选项”**。  
  
2.  展开“项目和解决方案”并单击“常规”。  
  
    > [!NOTE]
    >  即使未选中“显示所有设置”选项，“常规”节点也仍然可见。 如果要查看每个可用选项，请单击“显示所有设置”。  
  
3.  单击“显示高级生成配置”。  
  
4.  单击 **“确定”**。  
  
     现在可在“生成”菜单上使用“Configuration Manager”，并且“项目设计器”上会显示“配置”和“平台”列表。  
  
## <a name="see-also"></a>请参阅  
 [了解生成配置](../ide/understanding-build-configurations.md)   
 [编译和生成](../ide/compiling-and-building-in-visual-studio.md)



