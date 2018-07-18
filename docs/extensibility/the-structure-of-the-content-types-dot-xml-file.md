---
title: '[Content_types].xml 文件的结构 |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- content_types
- content types
- opc
- vsix
ms.assetid: 9c399598-b9fa-4da7-84b5-defbf82e9335
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 38e65f484411abcfb2acd78b124b77ff3f2c49cd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144562"
---
# <a name="the-structure-of-the-contenttypesxml-file"></a>[Content_types].xml 文件的结构
包含有关的 VSIX 包中的内容类型的信息。 Visual Studio 使用 [Content_Types].xml 文件来安装包，但它不会安装文件本身。  
  
> [!NOTE]
>  尽管本主题仅适用于使用 VSIX 包中的 [p e].xml 文件，[Content_Types].xml 文件类型是组成部分*开放式打包约定 (OPC)* 标准。 有关详细信息，请参阅[OPC: 新标准打包您数据的](http://go.microsoft.com/fwlink/?LinkID=148207)MSDN 网站上。  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述的根元素及其属性和子元素。  
  
### <a name="root-element"></a>根元素  
  
|元素|描述|  
|-------------|-----------------|  
|`Types`|包含枚举 VSIX 包中的文件类型的子元素。|  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`Xmlns`|（必选。）用于此 [Content_Types].xml 文件的架构位置。|  
  
### <a name="attribute-name-attribute"></a>{属性名称}属性  
  
|值|描述|  
|-----------|-----------------|  
|http://schemas.openformats.org/package/2006/content-types|内容类型架构的位置。|  
  
### <a name="child-elements"></a>子元素  
 `Types`元素可以包含任意数量的`Default`元素。  
  
|元素|描述|  
|-------------|-----------------|  
|`Default`|描述 VSIX 包中的内容类型。 包中的每个文件类型必须有其自己的`Default`元素。|  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`Extension`|VSIX 包中的文件文件扩展名。|  
|`ContentType`|描述此类是与文件扩展名相关联的内容。|  
  
### <a name="attribute-name-attribute"></a>{属性名称}属性  
 Visual Studio 识别以下`ContentType`关联的值`Extension`类型。  
  
|扩展名|ContentType|  
|---------------|-----------------|  
|txt|文本/无格式|  
|pkgdef|文本/无格式|  
|xml|text/xml|  
|vsixmanifest|text/xml|  
|htm 或 html|文本/html|  
|rtf|应用程序/rtf|  
|pdf|应用程序/pdf|  
|gif|图像/gif|  
|jpg 或 jpeg|图像/jpg|  
|Tiff|图像/tiff|  
|vsix|应用程序/zip|  
|zip|应用程序/zip|  
|dll|application/octet-stream|  
|所有其他文件类型|application/octet-stream|  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的 [Content_Types].xml 文件介绍了典型的 VSIX 包。  
  
### <a name="code"></a>代码  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<Types xmlns="http://schemas.openxmlformats.org/package/2006/content-types">  
    <Default Extension="vsixmanifest" ContentType="text/xml" />   
    <Default Extension="dll" ContentType="application/octet-stream" />   
    <Default Extension="png" ContentType="application/octet-stream" />   
    <Default Extension="txt" ContentType="text/plain" />   
    <Default Extension="pkgdef" ContentType="text/plain" />   
</Types>  
```  
  
## <a name="see-also"></a>另请参阅  
 [VSIX 包的剖析](../extensibility/anatomy-of-a-vsix-package.md)   
 [VSIX 扩展架构 1.0 引用](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [OPC： 用于打包你的数据新标准](http://go.microsoft.com/fwlink/?LinkID=148207)