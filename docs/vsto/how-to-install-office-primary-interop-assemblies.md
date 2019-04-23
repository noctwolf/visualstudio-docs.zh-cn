---
title: 如何：安装 Office 主互操作程序集
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- primary interop assemblies [Office development in Visual Studio], installing
- Office primary interop assemblies, installing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2ddba23ecb6007ff3b678932b118208742d1f0d4
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60109499"
---
# <a name="how-to-install-office-primary-interop-assemblies"></a>如何：安装 Office 主互操作程序集
  当你安装 Office 时，安装 Microsoft Office 主互操作程序集 (PIA)。

## <a name="to-install-the-pias-when-you-install-office"></a>安装 Office 时安装 PIA

1. 确保具有不超过 2.0 版本的 .NET Framework。

2. 安装 Microsoft Office，请确保 **.NET 可编程性支持**功能你想要扩展的应用程序选择 （默认安装中包括此功能）。

    > [!WARNING]
    >  默认情况下，PIA 的生成这样就不必将 Pia 分发给用户，作为使用 VSTO 外接程序或自定义的先决条件时你的解决方案中嵌入。

## <a name="see-also"></a>请参阅
- [Office 主互操作程序集](../vsto/office-primary-interop-assemblies.md)
- [如何：通过主互操作程序集的目标 Office 应用程序](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)
- [如何：配置计算机以开发 Office 解决方案](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)
- [如何：安装 Visual Studio Tools for Office runtime 可再发行组件](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)
- [Office 解决方案开发概述&#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)
- [开始&#40;Visual Studio 中的 Office 开发&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
