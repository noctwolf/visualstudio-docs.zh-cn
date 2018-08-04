---
title: CreatePkgDef 实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- package definition
- create pkgdef
- pkgdef
- createpkgdef
ms.assetid: c745cb76-47a6-49ff-9eed-16af0f748e35
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0809c7acde2959fb91aa964fec137f63a7a995dc
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2018
ms.locfileid: "39500691"
---
# <a name="createpkgdef-utility"></a>CreatePkgDef 实用工具
采用 Visual Studio 扩展中作为参数的.dll 文件，并创建 *.pkgdef*随附的文件 *.dll*文件。 *.Pkgdef*文件包含否则会在安装该扩展时写入到系统注册表的所有信息。  
  
> [!NOTE]
>  大部分自动包含在 Visual Studio SDK 中的项目模板创建 *.pkgdef*文件作为生成过程的一部分。 本文档适用于想要手动创建包或转换现有包使用的那些 *.pkgdef*部署。  
  
## <a name="syntax"></a>语法  
  
```  
CreatePkgDef /out=<FileName> [/codebase] [/assembly] <AssemblyPath>  
```  
  
## <a name="arguments"></a>自变量  
 **/ out =&lt;文件名&gt;**  
 必须的。 设置的名称 *.pkgdef*输出文件&lt;FileName&gt;。  
  
 /codebase  
 可选。 强制注册**基本代码**实用程序。  
  
 **/assembly**  
 强制注册**程序集**实用程序。  
  
 **&lt;AssemblyPath&gt;**  
 路径 *.dll*你想要生成的文件 *.pkgdef*。  
  
## <a name="remarks"></a>备注  
 通过使用扩展部署 *.pkgdef*文件将替换 Visual Studio 的早期版本的注册表要求。  
  
 *.Pkgdef*文件必须安装在以下位置之一： 

 - *%localappdata%\Microsoft\Visual Studio\14.0\Extensions\\* 
 
 - *%vsinstalldir%\Common7\IDE\Extensions\\*
    
 如果安装文件夹是 *%localappdata%\Microsoft\Visual Studio\14.0\Extensions\\*，扩展将识别的 Visual Studio 中，但默认情况下将禁用。 用户可以启用扩展，通过使用**扩展和更新**。 
   
 如果安装文件夹是 *%vsinstalldir%\Common7\IDE\Extensions\\*，默认情况下启用扩展。  
  
> [!NOTE]
>  **扩展和更新**工具不能用于访问扩展，除非它作为 VSIX 包的一部分安装。  
  
## <a name="see-also"></a>请参阅  
 [CreateExpInstance 实用工具](../../extensibility/internals/createexpinstance-utility.md)