---
title: 使用 DSL 库在 DSL 之间共享类
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5a48ba42982ea8f190fca2e13d714cb99cb01490
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31949454"
---
# <a name="sharing-classes-between-dsls-by-using-a-dsl-library"></a>使用 DSL 库在 DSL 之间共享类
在[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]可视化和建模 SDK，你可以创建，你可以导入到另一个 DSL 的 DSL 定义不完整。 这样可以考虑因素的类似模型的公共部分。

## <a name="creating-and-using-dsl-libraries"></a>创建和使用 DSL 库

#### <a name="to-create-a-dsl-library"></a>若要创建 DSL 库

1.  创建一个新的 DSL 项目，并选择 DSL 库解决方案模板。

     将使用一个空模型创建单个 DSL 项目。

2.  你可以添加域类、 关系、 形状等。

     库中的元素没有用于形成单个嵌入树。

     若要定义一种关系，可以使用导入程序，创建两个域类，并创建它们之间的关系。

     请考虑设置**继承修饰符**到的域类`Abstract`。

3.  您可以添加在 DSL 资源管理器，如连接生成器中定义的元素。

4.  您可以添加自定义需要其他代码，例如验证约束。

5.  单击**转换所有模板**。

6.  生成项目。

7.  让其他人有机会使用 DSL 分发时，必须提供编译的程序集 (DLL) 和文件`DslDefinition.dsl`。 你可以在下的文件夹中找到编译的程序集 `Dsl\bin\*`

#### <a name="to-import-a-dsl-library"></a>若要导入 DSL 库

1.  在另一个 DSL 定义中，在**DSL 资源管理器**，右键单击 DSL，根类，然后单击**添加新 DslLibrary 导入**。

2.  在属性窗口中，设置**文件路径**的库。 你可以使用相对或绝对路径。

     导入的库将显示在 DSL 资源管理器，在只读模式下。

3.  你可以使用导入的类作为基类。 在导入的 DSL，创建域类并在属性窗口中，设置**基类**到导入的类。

4.  单击转换所有模板。

5.  DSL 项目中，添加对由 DSL 库项目生成的程序集 (DLL) 的引用。

6.  生成解决方案。

 DSL 库可以导入其他库。 当你导入的库，其导入也会自动出现在 DSL 资源管理器。

## <a name="see-also"></a>请参阅

- [如何定义域特定语言](../modeling/how-to-define-a-domain-specific-language.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
