---
title: 管理 VSPackages |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, delayed loading
- delay loading
- VSPackages, loading
ms.assetid: 386e0ce5-4107-4164-b0cd-1cf43eb5e7cf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a316d2af6ecb76c573cfb43e1334df1933a2989b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62856224"
---
# <a name="manage-vspackages"></a>管理 VSPackage
在大多数情况下，您不必担心如何管理 Vspackage，因为项目和项模板注册，并自动加载包。 但是，在某些情况下您可能需要了解详细信息，以便管理您的包。

## <a name="use-the-experimental-instance"></a>使用实验实例
 若要了解有关实验实例的详细信息，请参阅[实验实例](../extensibility/the-experimental-instance.md)。

## <a name="register-and-unregister-vspackages"></a>注册和注销 Vspackage
 若要了解如何注册和注销 Vspackage 和其他类型的扩展，请参阅[注册和注销 Vspackage](../extensibility/registering-and-unregistering-vspackages.md)。

## <a name="load-a-vspackage"></a>加载 VSPackage
 Vspackage 可以设置为自动加载特定 CMDUICONTEXT GUID 处于开启状态。 有关详细信息，请参阅[加载 Vspackage](../extensibility/loading-vspackages.md)。

## <a name="use-asyncpackage-to-load-vspackages-in-the-background"></a>使用 AsyncPackage 在后台加载 Vspackage
 `AsyncPackage`类就能更好的 UI 响应能力，在 Visual Studio 中在后台线程上的包加载。 有关详细信息，请参阅[如何：使用 AsyncPackage 加载 Vspackage，在后台](../extensibility/how-to-use-asyncpackage-to-load-vspackages-in-the-background.md)。

## <a name="rule-based-ui-context-for-extensions"></a>扩展的基于规则的 UI 上下文
 基于规则的 UI 上下文允许扩展创建者定义的 UI 上下文激活和相关联的 Vspackage 加载的精确条件。 有关详细信息，请参阅[如何：用于 Visual Studio 扩展的基于规则的 UI 上下文](../extensibility/how-to-use-rule-based-ui-context-for-visual-studio-extensions.md)。

## <a name="diagnose-extension-performance"></a>诊断扩展性能
扩展可能会影响启动和解决方案负载性能。 了解如何计算 Visual Studio 扩展的影响，以及如何可在进行分析本地测试作为一种性能影响扩展，扩展可能会显示。 有关详细信息，请参阅[如何：诊断扩展性能](how-to-diagnose-extension-performance.md)。

## <a name="troubleshoot-vspackages"></a>对 Vspackage 进行故障排除
 找出以进行故障排除 Vspackage 不加载或遇到错误的技术：[对 Vspackage 进行故障排除](../extensibility/troubleshooting-vspackages.md)

## <a name="see-also"></a>请参阅
- [VSPackage](../extensibility/internals/vspackages.md)