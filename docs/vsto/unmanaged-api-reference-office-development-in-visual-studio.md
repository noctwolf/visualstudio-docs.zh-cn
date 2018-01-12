---
title: "非托管 API 参考 （Visual Studio 中的 Office 开发） |Microsoft 文档"
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
helpviewer_keywords:
- Office development in Visual Studio, reference
- Office development in Visual Studio, unmanaged API reference
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 640e292719f8d466ba21cc449ea624527b50bcf0
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="unmanaged-api-reference-office-development-in-visual-studio"></a>非托管 API 参考（Visual Studio 中的 Office 开发）
  从 2007 Microsoft Office system 开始，Office 应用程序使用[IManagedAddin 接口](../vsto/imanagedaddin-interface.md)接口来调用的 VSTO 外接程序加载程序组件附带[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]。 此组件用于帮助加载托管 VSTO 外接程序。可以通过实现此接口来创建自己的 VSTO 外接程序加载程序组件。  
  
> [!NOTE]  
>  开发扩展的 Office 体验跨解决方案是否有兴趣[多个平台](https://dev.office.com/add-in-availability)？ 查看全新[Office 外接程序模型](https://dev.office.com/docs/add-ins/overview/office-add-ins)。 Office 外接程序具有内存占用较小与 VSTO 外接程序和解决方案，相比，并且你可以通过使用几乎任何 web 编程技术，例如 HTML5、 JavaScript、 CSS3 和 XML 生成它们。  
  
## <a name="in-this-section"></a>本节内容  
 [IManagedAddin Interface](../vsto/imanagedaddin-interface.md)  
 一种 COM 接口，可以通过实现该接口来在 Office 应用程序中加载和卸载 VSTO 托管外接程序。  
  
  