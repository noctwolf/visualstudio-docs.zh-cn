---
title: 常规项目属性（Android C++ 生成文件）| Microsoft Docs
ms.custom: ''
ms.date: 10/23/2017
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: f76d717c-56ed-4373-8cf9-9bd1a053a4cd
author: corob
ms.author: mblome
manager: douge
f1_keywords:
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.ConfigurationType
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: cfc1655adbd9377f1aeeec60afc799f342b4498d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31060075"
---
# <a name="general-project-properties-android-c-makefile"></a>常规项目属性（Android C++ 生成文件）

属性 | 描述 | 选项
--- | ---| ---
输出目录 | 指定输出文件目录的相对路径；可以包含环境变量。
中间目录 | 指定中间文件目录的相对路径；可以包含环境变量。
生成日志文件 | 指定启用生成日志时要写入的生成日志文件。
配置类型 | 指定此配置生成的输出类型。 | 动态库 (.so) - 动态库 (.so)<br>静态库 (.a) - 静态库 (.a)<br>实用工具 - 实用程序<br>生成文件 - 生成文件<br>
