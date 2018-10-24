---
title: LocalizedName 元素 （VSIX 语言包架构） |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57b7f502-3b04-42d9-90d5-f57772a7c757
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d17ce9db334d3b2cc8b6c892784b10d42eba07ad
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49832415"
---
# <a name="localizedname-element-vsix-language-pack-schema"></a>LocalizedName 元素 （VSIX 语言包架构）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

必须的。 要安装的扩展插件的本地化的名称。  
  
## <a name="syntax"></a>语法  
  
```  
<Name>Localized name of the extension</Name>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|无||  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|无||  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[VSIX LanguagePack 元素](../extensibility/vsixlanguagepack-element-vsix-language-pack-schema.md)|必须的。 VSIX 语言包中提供的根元素。|  
  
## <a name="text-value"></a>文本值  
 必须的。 在目标语言的语言包的名称。  
  
## <a name="element-information"></a>元素信息  
  
|                 |                                                           |
|-----------------|-----------------------------------------------------------|
|    命名空间    | http://schemas.microsoft.com/developer/vsx-schema-lp/2010 |
|   架构名称   |                 VSIX 语言包架构                 |
| 验证文件 |                VSIXLanguagePackSchema.xsd                 |
|  可以为空   |                      不适用                       |
  
## <a name="see-also"></a>请参阅  
 [VSX 语言包架构参考](../extensibility/vsx-language-pack-schema-reference.md)   
 [本地化 VSIX 包](../extensibility/localizing-vsix-packages.md)   
 [VSIX 扩展架构 1.0 参考](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)

