---
title: 非托管的 API 参考 （Visual Studio 中的 Office 开发）
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, reference
- Office development in Visual Studio, unmanaged API reference
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9b0f48ea5997c2c8c2dd7d90eebde8322fad8a7a
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "35670425"
---
# <a name="unmanaged-api-reference-office-development-in-visual-studio"></a>非托管的 API 参考 （Visual Studio 中的 Office 开发）
  从 2007 Microsoft Office system 开始，Office 应用程序使用[IManagedAddin 接口](../vsto/imanagedaddin-interface.md)接口以调入 VSTO 外接程序加载程序组件附带[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]。 此组件用于帮助加载托管 VSTO 加载项。可以通过实现此接口来创建自己的 VSTO 外接程序加载程序组件。  
  
> [!NOTE]  
>  开发扩展的 Office 体验跨解决方案是否有兴趣[多个平台](https://dev.office.com/add-in-availability)？ 查看全新[Office 外接程序模型](https://dev.office.com/docs/add-ins/overview/office-add-ins)。 Office 外接程序具有较小的需求量与 VSTO 外接程序和解决方案，相比，您可以使用几乎任何 web 编程技术，HTML5、 JavaScript、 CSS3 和 XML 等来生成。  
  
## <a name="in-this-section"></a>本节内容  
 [IManagedAddin 接口](../vsto/imanagedaddin-interface.md)  
 一种 COM 接口，可以通过实现该接口来在 Office 应用程序中加载和卸载 VSTO 托管外接程序。  
  
  