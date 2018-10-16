---
title: 字符串用作键用于查找源代码管理插件 |Microsoft Docs
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
- source control plug-ins, strings used for finding
ms.assetid: c1e31f76-42a1-4c3d-afb2-664044ef12fd
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5f49ac150af84cdd5dfae52e905cb353722b0ed0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49243628"
---
# <a name="strings-used-as-keys-for-finding-a-source-control-plug-in"></a>作为用于查找源代码管理插件的密钥的字符串
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

以下字符串是用于访问注册表，以了解有关源代码管理插件的项。  
  
 `STR_SCC_PROVIDER_REG_LOCATION``STR_PROVIDERREGKEY`， `STR_SCCPROVIDERPATH`，和`STR_SCCPROVIDERNAME`是注册表项或值用于将 DLL 注册为 Visual Studio 源代码管理插件。  
  
 `SCC_PROJECTNAME_KEY``SCC_PROJECTAUX_KEY`， `SCC_KEY, SCC_FILE_SIGNATURE`，和`SCC_STATUS_FILE`用于描述 MSSCCPRJ 的格式。SCC 文件。  
  
## <a name="string-keys-and-values"></a>字符串键和值  
  
|键|“值”|  
|---------|-----------|  
|`STR_SCC_PROVIDER_REG_LOCATION`|Software\SourceCodeControlProvider|  
|`STR_PROVIDERREGKEY`|ProviderRegKey|  
|`STR_SCCPROVIDERPATH`|SCCServerPath|  
|`STR_SCCPROVIDERNAME`|SCCServerName|  
|`STR_SCC_INI_SECTION`|源代码管理|  
|`STR_SCC_INI_KEY`|SourceCodeControlProvider|  
|`SCC_PROJECTNAME_KEY`|SCC_Project_Name|  
|`SCC_PROJECTAUX_KEY`|SCC_Aux_Path|  
|`SCC_STATUS_FILE`|MSSCCPRJ。源代码管理|  
|`SCC_KEY`|源代码管理|  
|`SCC_FILE_SIGNATURE`|源代码控制文件|  
|`SCC_NSE`|Namespace 扩展|  
|`SCC_NSE_PREFIX`|协议前缀|  
|`SCC_NSE_DisableOpenSCC`|DisableOpenFromSourceControl|  
|`STR_SCCHELPCOLLECTION`|HelpCollection|  
|`STR_UI_LANGUAGE`|UILanguage|  
|`STR_SRCSAFE_ROOT_KEY`|Software\Microsoft\SourceSafe|  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件](../extensibility/source-control-plug-ins.md)   
 [如何： 安装源代码管理插件](../extensibility/internals/how-to-install-a-source-control-plug-in.md)   
 [MSSCCPRJ.SCC 文件](../extensibility/mssccprj-scc-file.md)

