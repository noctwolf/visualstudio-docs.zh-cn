---
title: 图像形状的属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.selectimagedialog
- vs.dsltools.dsldesigner.imageshape
helpviewer_keywords:
- Domain-Specific Language, image shape
ms.assetid: 9ce00ccd-07f2-4640-ac96-2a60481d0d72
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 6b324e82608a79f8f57762e2538b401c794d831c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49304091"
---
# <a name="properties-of-image-shapes"></a>图像形状的属性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

图像形状可用于指定域类生成的设计器中的显示方式。 通过设置来定义了图像形状`Image`类预定义的图像文件的属性。 支持以下格式：  
  
-   .gif  
  
-   .jpg  
  
-   .jpeg  
  
-   .bmp  
  
-   .wmf  
  
-   .emf  
  
-   .png  
  
 默认情况下，设计器的资源文件，如图像文件位于**资源**中的文件夹**Dsl**项目。  
  
 有关详细信息，请参阅[如何定义特定于域的语言](../modeling/how-to-define-a-domain-specific-language.md)。 有关如何使用这些属性的详细信息，请参阅[自定义和扩展域特定语言](../modeling/customizing-and-extending-a-domain-specific-language.md)。  
  
 图像形状具有下表中列出的属性。  
  
|属性|描述|默认|  
|--------------|-----------------|-------------|  
|填充颜色|此形状的填充颜色。|白色|  
|填充渐变模式|此形状的填充渐变模式。|水平|  
|具有默认的连接点|如果`True`、 形状将使用顶部、 底部、 左侧、 和中生成的设计器的正确的连接点。|False|  
|轮廓颜色|此形状的轮廓颜色。|黑色|  
|边框虚线线型|此形状 （纯色、 短划线、 圆点、 DashDot、 DashDotDot 或自定义） 的边框虚线线型。|单色|  
|轮廓粗细|此形状的边框粗细。|0.03125|  
|文本颜色|使用与此形状相关联的文本修饰器的颜色。|黑色|  
|访问修饰符|几何形状 （公共或内部） 的访问修饰符。|Public|  
|自定义特性|用于将属性添加到此形状从生成的源代码类。|\<无 >|  
|生成双派生|如果`True`，将生成的基类和一个分部类 （以支持通过重写自定义）。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|False|  
|具有自定义构造函数|如果`True`，将在源代码中提供自定义构造函数。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|False|  
|继承修饰符|说明图像形状从生成的源代码类继承的类型 (`none`，`abstract`或`sealed`)。|无|  
|基本图像形状|此形状的基类。|(无)|  
|name|此形状的名称。|当前名称|  
|命名空间|与此形状相关联的命名空间。|当前命名空间|  
|工具提示类型|其中定义工具提示的位置 （固定的变量，或无）。 如果固定，然后的值`Fixed Tooltip Text`属性用作工具提示; 如果变量，然后在工具提示中定义自定义代码。|无|  
|说明|与此形状相关联的非正式说明。|\<无 >|  
|初始高度|此形状，以英寸为单位的初始高度。|1|  
|初始宽度|此形状，以英寸为单位的初始宽度。|1.5|  
|作为属性公开的填充颜色<br /><br /> 公开的填充渐变模式<br /><br /> 作为属性公开轮廓颜色<br /><br /> 作为属性公开边框虚线线型<br /><br /> 公开为属性的边框粗细<br /><br /> 公开文本颜色|如果`True`，用户可以设置形状的规定的属性。 若要将此项设置，请右键单击形状定义，然后单击**公开添加**。|False|  
|描述|用于记录生成的设计器。|\<无 >|  
|显示名称|将此形状的生成设计器中显示的名称。|\<无 >|  
|固定工具提示文本|用于固定工具提示文本。|\<无 >|  
|帮助关键字|用于索引此元素的 F1 帮助关键字。|\<无 >|  
|图像|用于此形状的图像文件路径。|\<无 >|  
  
## <a name="see-also"></a>请参阅  
 [域特定语言工具术语表](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



