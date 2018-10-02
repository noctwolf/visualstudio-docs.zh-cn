---
title: 使用 DSL 库在 Dsl 之间共享类 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 509bd96b-3e66-47f4-8642-771421d0d0d5
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: a4ec7820be2cc4f308582e71f3ba64ded5c296e7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478819"
---
# <a name="sharing-classes-between-dsls-by-using-a-dsl-library"></a>使用 DSL 库在 DSL 之间共享类
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[使用 DSL 库在 Dsl 之间共享类](https://docs.microsoft.com/visualstudio/modeling/sharing-classes-between-dsls-by-using-a-dsl-library)。  
  
在[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]可视化和建模 SDK，可以创建可导入到另一个 DSL 的 DSL 定义不完整。 这允许您考虑通用部分类似的模型。  
  
## <a name="creating-and-using-dsl-libraries"></a>创建和使用 DSL 库  
  
#### <a name="to-create-a-dsl-library"></a>若要创建的 DSL 库  
  
1.  创建一个新的 DSL 项目，并选择的 Dsl 解决方案模板。  
  
     使用空模型，将创建单个的 DSL 项目。  
  
2.  您可以添加域类、 关系、 形状等。  
  
     库中的元素不需要形成单个嵌入树。  
  
     若要定义一种关系，可以使用导入程序，创建两个域类，并创建它们之间的关系。  
  
     请考虑设置**继承修饰符**到的域类的`Abstract`。  
  
3.  您可以添加在 DSL 资源管理器，如连接生成器中定义的元素。  
  
4.  您可以添加自定义项，需要额外的代码，例如验证约束。  
  
5.  单击**转换所有模板**。  
  
6.  生成项目。  
  
7.  当你将分发的其他人使用 DSL 时，必须提供编译的程序集 (DLL) 和文件`DslDefinition.dsl`。 可以下的文件夹中找到的已编译的程序集 `Dsl\bin\*`  
  
#### <a name="to-import-a-dsl-library"></a>将 DSL 库导入  
  
1.  在另一个 DSL 定义中，在**DSL 资源管理器**，右键单击 DSL 的根类，然后单击**添加新的 DslLibrary 导入**。  
  
2.  在属性窗口中设置**文件路径**的库。 可以使用相对或绝对路径。  
  
     导入的库在 DSL 资源管理器，显示在只读模式下。  
  
3.  您可以使用导入的类作为基类。 在导入的 DSL 中，创建一个域类，在属性窗口中，设置**基类**到导入的类。  
  
4.  单击转换所有模板。  
  
5.  将对由 DSL 库项目生成的程序集 (DLL) 的引用添加到 DSL 项目中。  
  
6.  生成解决方案。  
  
 DSL 库在可以导入其他库。 当导入一个库时，其导入也会自动显示在 DSL 资源管理器。  
  
## <a name="see-also"></a>请参阅  
 [如何定义域特定语言](../modeling/how-to-define-a-domain-specific-language.md)



