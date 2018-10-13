---
title: 适用于 Configuration 和 SelectedItem 对象的自动化 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], SelectedItem object
- automation [Visual Studio SDK], builds
ms.assetid: 120377f1-51aa-4445-b2f7-06ab7fc2b47f
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 80c67567a3e9ed3fd482a9a88f6d52cddcc0a3e5
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49185414"
---
# <a name="automation-for-configuration-and-selecteditem-objects"></a>Configuration 和 SelectedItem 对象的自动化
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

你可以自动生成和中的选定的项进程[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。  
  
## <a name="automation-for-builds"></a>生成自动化  
 生成或配置已实现时提供的自动化模型<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider>。 有关详细信息，请参阅[了解生成配置](../../ide/understanding-build-configurations.md)。  
  
 如果你创建 VSPackage，并且想要控制的配置选项，必须使用自动化模型。  
  
## <a name="automation-for-selecteditem"></a>SelectedItem 的自动化  
 不需要为提供一个实现`SelectedItem`对象，因为 Visual Studio 包含的标准实现。 但是，可以实现`SelectedItem`对象如果您更喜欢。 必须实现一个对象，包含`SelectedItem`接口，并返回到调用的响应<xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A>VSITEMID 方法设置为<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A>   
 [参与自动化模型](../../extensibility/internals/contributing-to-the-automation-model.md)   
 [了解生成配置](../../ide/understanding-build-configurations.md)

