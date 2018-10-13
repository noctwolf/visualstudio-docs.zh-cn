---
title: 清单： 创建新的项目类型 |Microsoft Docs
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
- projects [Visual Studio SDK], creating new types
- project types, checklist for creating
ms.assetid: 29eb9c3b-1933-4741-aa85-65a33f0825ba
caps.latest.revision: 24
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8047ea1aeb6a163a627f9198ca3f6731419949ae
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49285982"
---
# <a name="checklist-creating-new-project-types"></a>清单：新建项目类型
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

必须完成多个任务以创建新的项目类型。 下列清单提供了这些任务的指南。  
  
1.  设计新的项目类型的功能。 有关详细信息，请参阅[项目类型设计决策](../../extensibility/internals/project-type-design-decisions.md)。  
  
2.  确定将哪个编辑器用于代码和其他项目元素。 可以使用的核心或标准编辑器，也可以创建和使用特定于项目的编辑器。 有关详细信息，请参阅[创建自定义编辑器和设计器](../../extensibility/creating-custom-editors-and-designers.md)并[如何： 打开项目特定的编辑器](../../extensibility/how-to-open-project-specific-editors.md)。  
  
3.  确定项目项都将具有中的参与等级**类视图**并**对象浏览器**。 有关详细信息，请参阅[支持符号浏览工具](../../extensibility/internals/supporting-symbol-browsing-tools.md)。  
  
4.  派生新类根据先前创建的项目和项目项的设计决策。  
  
5.  编写以下项目类型组件的代码：  
  
    -   项目工厂，来管理创建新项目和打开现有项目。 有关详细信息，请参阅[创建项目实例通过使用项目工厂](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)。  
  
    -   项目层次结构和命令处理。 有关详细信息，请参阅[不在生成： 使用 HierUtil7 项目类以实现项目类型 （c + +）](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346)，[的项目模型元素](../../extensibility/internals/elements-of-a-project-model.md)，[项目模型核心组件](../../extensibility/internals/project-model-core-components.md)和[MenuCommands 与。OleMenuCommands](../../misc/menucommands-vs-olemenucommands.md)。  
  
    -   项目项管理，包括添加到项目**新的项目**对话框。 有关详细信息，请参阅[添加项目和项目项模板](../../extensibility/internals/adding-project-and-project-item-templates.md)并[注册项目和项模板](../../extensibility/internals/registering-project-and-item-templates.md)。  
  
    -   暂留的项目状态和各个项。 有关详细信息，请参阅[打开和保存项目项](../../extensibility/internals/opening-and-saving-project-items.md)。 有关持久性的解决方案的信息，请参阅[解决方案](../../extensibility/internals/solutions.md)。  
  
    -   配置独立的属性在属性窗口中显示。 有关详细信息，请参阅[扩展属性](../../extensibility/internals/extending-properties.md)。  
  
    -   在属性页以显示依赖于配置的属性中实现的项目配置属性。 有关详细信息，请参阅[管理配置选项](../../extensibility/internals/managing-configuration-options.md)。  
  
    -   枚举用于部署的输出。 有关详细信息，请参阅[输出的项目配置](../../extensibility/internals/project-configuration-for-output.md)。  
  
    -   项目启动服务。 有关详细信息，请参阅[项目模型的元素](../../extensibility/internals/elements-of-a-project-model.md)并[项目模型核心组件](../../extensibility/internals/project-model-core-components.md)。  
  
    -   对象或从派生的类`IDispatch`，可用于自动化。  
  
    -   XML 命令表格 (.vsct) 文件。 有关详细信息，请参阅 [Visual Studio Command Table (.Vsct) Files](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)。  
  
6.  测试、 调试和启动您的项目类型。  
  
7.  显示的项目中**项目**选项卡**添加引用**对话框中，通过设置`VARIANT_TRUE`的值作为`VSHPROPID_ShowProjInSolutionPage`。 有关详细信息，请参阅 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 和 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>。  
  
8.  创建用于安装你的 Vspackage 的 Microsoft Installer (.msi) 文件。 有关详细信息，请参阅[使用 Windows Installer 安装 Vspackage](../../extensibility/internals/installing-vspackages-with-windows-installer.md)，[注册项目类型](../../extensibility/internals/registering-a-project-type.md)，并[Vspackage](../../extensibility/internals/vspackages.md)。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中的层次结构](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [何时创建项目类型](../../extensibility/internals/when-to-create-project-types.md)   
 [创建项目类型](../../extensibility/internals/creating-project-types.md)

