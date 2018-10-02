---
title: CreateExpInstance 实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- experimental builds
- experimental hive
- experimental instance
- createexpinstance
- createexpinst
ms.assetid: 03779774-9401-49ae-997c-0c3ab25ed0d5
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f9b08ba5ac68a09f6c44937634375add3065e5e8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476693"
---
# <a name="createexpinstance-utility"></a>CreateExpInstance 实用工具
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CreateExpInstance 实用工具](https://docs.microsoft.com/visualstudio/extensibility/internals/createexpinstance-utility)。  
  
重置，请使用 CreateExpInstance 实用工具创建，或删除 Visual Studio 的实验实例。 可以使用实验实例来调试和测试 Visual Studio 扩展，而无需更改基础产品。  
  
## <a name="syntax"></a>语法  
  
```  
CreateExpInstance.exe [/Create | /Reset | /Clean] /VSInstance=VsInstance /RootSuffix=Suffix  
```  
  
#### <a name="parameters"></a>参数  
 / 创建  
 创建实验实例。  
  
 / 重置  
 删除实验实例，然后创建一个新。  
  
 /Clean  
 删除实验实例。  
  
 / VSInstance  
 包含要复制的基本 Visual Studio 实例的目录的名称。  
  
 / RootSuffix  
 要追加到实验实例目录的名称的后缀。  
  
## <a name="remarks"></a>备注  
 当您正在从事 Visual Studio 扩展时，可以按 f5 键以打开默认实验实例，并安装当前的扩展。 如果没有实验实例不可用，Visual Studio 将创建一个具有默认设置。  
  
 实验实例的默认位置取决于 Visual Studio 版本号。 例如，对于 Visual Studio 2015 中，位置是 %localappdata%\Microsoft\VisualStudio\14.0Exp\ 中的目录位置的所有文件被都视为该实例的一部分。 将由 Visual Studio 加载任何其他实验实例，除非目录名称已更改为默认位置。  
  
 在打开的实验实例时，visual Studio 不访问系统注册表。 这不同于早期版本的 Visual Studio 中，使用注册表配置单元的实验性版本。  
  
 CreateExpInstance 实用工具将替换，VsRegEx 实用程序。  
  
 以下示例重置默认的 Visual Studio 的实验实例。  
  
 **CreateExpInstance.exe /Reset /VSInstance = 14.0 /RootSuffix = Exp**  
  
## <a name="see-also"></a>请参阅  
 [发布产品](../../misc/releasing-a-visual-studio-integration-product.md)

