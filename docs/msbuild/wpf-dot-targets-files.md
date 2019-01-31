---
title: WPF .Targets 文件 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- combining tasks into a .targets file to build an MSBuild project [WPF MSBuild]
- WPF .targets files [WPF MSBuild], introduction
- WPF .targets files [WPF MSBuild]
ms.assetid: e85a3ff4-dedd-4ff4-9b22-3a1e94755362
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ade955f53f7e3d3823580934f623c9b0157f04c9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55042224"
---
# <a name="wpf-targets-files"></a>WPF .targets 文件
[!INCLUDE[TLA#tla_winclient](../misc/includes/tlasharptla_winclient_md.md)] 通过添加一组特定于 [!INCLUDE[TLA2#tla_wpf](../msbuild/includes/tla2sharptla_wpf_md.md)] 的任务（任务被合并到一个特殊的 .targets 文件 Microsoft.WinFX.targets）来扩展 [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)]。 此文件合并了在 [!INCLUDE[TLA#tla_winclient](../misc/includes/tlasharptla_winclient_md.md)] 中生成 [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] 项目所需的一组 [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] 任务。  
  
## <a name="see-also"></a>请参阅  
 [MSBuild .targets 文件](../msbuild/msbuild-dot-targets-files.md)   
 [MSBuild 参考](../msbuild/msbuild-reference.md)   
 [生成 WPF 应用程序 (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)