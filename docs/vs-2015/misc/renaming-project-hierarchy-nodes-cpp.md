---
title: 重命名项目层次结构节点 （c + +） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HierUtil7 sample [Visual Studio SDK], renaming project nodes
- project nodes, renaming in HierUtil7 sample
ms.assetid: cea5968e-e9f8-41a5-b068-622df542247c
caps.latest.revision: 12
manager: douge
ms.openlocfilehash: 57e647f2926452fe32b4d3975b0cd151d0fc9823
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479335"
---
# <a name="renaming-project-hierarchy-nodes-c"></a>重命名项目层次结构节点 (C++)
可以使用非托管 c + + HierUtil7 项目框架重命名项目文件夹层次结构节点。 有关详细信息，请参阅[HierUtil7 示例](http://msdn.microsoft.com/en-us/29c15184-a70c-4813-86c2-fb1d47442d11)。  
  
## <a name="expanding-the-hierarchy-node"></a>展开层次结构节点  
  
#### <a name="to-expand-the-hierarchy-node-and-rename-the-folder"></a>若要展开层次结构节点，然后重命名文件夹  
  
1.  使用以下方法选择层次结构节点：  
  
    ```  
    IfFailGo(pNode->ExtExpand(EXPF_SelectItem, GUID_MacroExplorer));  
    ```  
  
     `pNode` 是对应于该文件夹的层次结构容器并`EXPF_SelectItem`来自<xref:Microsoft.VisualStudio.Shell.Interop.EXPANDFLAGS>枚举。 `GUID_MacroExplorer` Vsshell.idl 中定义的 GUID 常量，例如`rguidPersistenceSlot`的函数签名中`ExtExpand`Hu_node.h 中定义。  
  
    ```  
    HRESULT ExtExpand(EXPANDFLAGS expandflags, REFGUID rguidPersistenceSlot = GUID_SolutionExplorer) const;  
    ```  
  
     您可以在文件夹中，找到 Hu_node.h 文件\<安装根路径 > \Program Files\VSIP 8.0\EnvSDK\common\hierutil7:  
  
2.  重命名命令发布使用重命名文件夹 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.PostExecCommand%2A>  
  
    ```  
    IfFailGo(srpVsUIShell->PostExecCommand(&guidVSStd97, cmdidRename, 0, NULL));  
    ```  
  
     `srpVsUIShell` 是<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>指针： `<IVsUIShell>``srpVsUIShell`。 `guiVSStd97` 是的命令组的唯一标识符命令`cmdidRename`所属 Vsshlids.h 中定义。  
  
## <a name="see-also"></a>请参阅  
 [创建项目类型](../extensibility/internals/creating-project-types.md)   
 [VSSDK 示例](../misc/vssdk-samples.md)