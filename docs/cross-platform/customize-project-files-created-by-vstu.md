---
title: "自定义 VSTU 创建的项目文件 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60b8cc1d-cacc-404d-b768-77e81bc354f8
caps.latest.revision: "2"
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload: unity
ms.openlocfilehash: ec48b219b0d70455154f43584f7b00e85dd42992
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="customize-project-files-created-by-vstu"></a>自定义 VSTU 创建的项目文件
Visual Studio Tools for Unity 在项目文件生成期间提供 Unity 样式回调。 注册 `VisualStudioIntegration.ProjectFileGeneration` 事件以在生成项目文件时对其进行修改。  

## <a name="demonstrates"></a>演示  
 如何自定义由 Visual Studio Tools for Unity 生成的 Visual Studio 项目文件。  

## <a name="example"></a>示例  

```csharp  
using System;  
using System.IO;  
using System.Linq;  
using System.Text;  
using System.Xml.Linq;  

using UnityEngine;  
using UnityEditor;  

using SyntaxTree.VisualStudio.Unity.Bridge;  

[InitializeOnLoad]  
public class ProjectFileHook  
{  
    // necessary for XLinq to save the xml project file in utf8  
    class Utf8StringWriter : StringWriter  
    {  
        public override Encoding Encoding  
        {  
            get { return Encoding.UTF8; }  
        }  
    }  

    static ProjectFileHook()  
    {  
        ProjectFilesGenerator.ProjectFileGeneration += (string name, string content) =>  
        {  
            // parse the document and make some changes  
            var document = XDocument.Parse(content);  
            document.Root.Add(new XComment("FIX ME"));  

            // save the changes using the Utf8StringWriter  
            var str = new Utf8StringWriter();  
            document.Save(str);  

            return str.ToString();  
        };  
    }  
}  
```  

## <a name="see-also"></a>请参阅  
 [示例：日志回调](../cross-platform/share-the-unity-log-callback-with-vstu.md)
