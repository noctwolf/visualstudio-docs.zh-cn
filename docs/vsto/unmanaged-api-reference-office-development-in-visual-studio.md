---
title: 非托管的 API 参考 （Visual Studio 中的 Office 开发）
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, reference
- Office development in Visual Studio, unmanaged API reference
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 238ed42d48903d2d0ef26384245cff80785a8ebb
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56643699"
---
# <a name="unmanaged-api-reference-office-development-in-visual-studio"></a>非托管的 API 参考 （Visual Studio 中的 Office 开发）

从 2007 Microsoft Office system 开始，Office 应用程序使用[IManagedAddin 接口](../vsto/imanagedaddin-interface.md)接口以调入 VSTO 外接程序加载程序组件附带[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]。 此组件用于帮助加载托管 VSTO 加载项。可以通过实现此接口来创建自己的 VSTO 外接程序加载程序组件。

> [!NOTE]
> 开发扩展的 Office 体验跨解决方案是否有兴趣[多个平台](https://dev.office.com/add-in-availability)？ 查看全新[Office 外接程序模型](https://dev.office.com/docs/add-ins/overview/office-add-ins)。 Office 外接程序具有较小的需求量与 VSTO 外接程序和解决方案，相比，您可以使用几乎任何 web 编程技术，HTML5、 JavaScript、 CSS3 和 XML 等来生成。

## <a name="in-this-section"></a>本节内容

[IManagedAddin 接口](../vsto/imanagedaddin-interface.md)

一种 COM 接口，可以通过实现该接口来在 Office 应用程序中加载和卸载 VSTO 托管外接程序。
