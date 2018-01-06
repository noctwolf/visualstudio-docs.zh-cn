---
title: "源控制运行时详细信息 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control [Visual Studio SDK], runtime details
ms.assetid: 1acd30e0-f98c-4bde-b9cd-4076845887df
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9b27aa56cdcf48ded56f9a43e40a1e65f3491536
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="source-control-runtime-details"></a>源控制运行时详细信息
当用户在项目源代码管理，或通过自动化控制器，如向导中添加文件时，项目将添加到源代码管理。 项目未指定为自身很受源代码管理;它支持源代码管理，但必须手动添加到它。  
  
## <a name="registering-with-a-source-control-package"></a>注册源代码管理包  
 当你的项目中的文件添加到源代码管理时，则环境将调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>来为你提供四个用作 cookie 的源代码管理系统的不透明字符串。 在你的项目文件中存储这些字符串。 这些字符串应传递到源控件存根 （管理源代码管理包的 Visual Studio 组件） 启动的项目类型通过调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>。 这又依次加载相应的源代码管理包并将转发到其实现中调用`IVsSccManager2::RegisterSccProject`。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>   
 [支持源代码管理](../../extensibility/internals/supporting-source-control.md)