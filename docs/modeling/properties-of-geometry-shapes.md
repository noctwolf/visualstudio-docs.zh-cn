---
title: 几何形状的属性
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.geometryshape
helpviewer_keywords:
- Domain-Specific Language, geometry shape
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b1006fdb766c4c375c93a97f17cccd4e95568677
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62998969"
---
# <a name="properties-of-geometry-shapes"></a>几何形状的属性
几何形状可用于指定域类的实例中的域特定语言的显示方式。 有关详细信息，请参阅[如何定义特定于域的语言](../modeling/how-to-define-a-domain-specific-language.md)。 有关如何使用这些属性的详细信息，请参阅[自定义和扩展域特定语言](../modeling/customizing-and-extending-a-domain-specific-language.md)。

 几何形状具有下表中列出的属性。

|属性|描述|默认|
|-|-|-|
|填充颜色|此形状的填充颜色。|白色|
|填充渐变模式|此形状 （水平、 垂直、 正向对角线后, 向对角线，或无） 填充渐变模式。|水平|
|geometry|此形状 （矩形、 圆角矩形、 椭圆或圆） 的几何图形。|矩形|
|具有默认的连接点|如果`True`、 形状将使用顶部、 底部、 左侧、 和中生成的设计器的正确的连接点。|False|
|轮廓颜色|此形状的轮廓颜色。|黑色|
|边框虚线线型|此形状 （纯色、 短划线、 圆点、 DashDot、 DashDotDot 或自定义） 的边框虚线线型。|单色|
|轮廓粗细|此形状的边框粗细。|0.03125|
|文本颜色|使用与此形状相关联的文本修饰器的颜色。|黑色|
|访问修饰符|类 （公共或内部） 的访问修饰符。|Public|
|自定义特性|用于将属性添加到可生成对此形状的源代码类。|\<none>|
|生成双派生|如果`True`，将生成的基类和一个分部类 （以支持通过重写自定义）。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|False|
|具有自定义构造函数|如果`True`，将在源代码中提供自定义构造函数。 有关详细信息，请参阅[重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|False|
|继承修饰符|介绍的形状从生成的源代码类的继承的类型 (`none`，`abstract`或`sealed`)。|无|
|基本几何形状|此形状的基类。|(无)|
|名称|此形状的名称。|当前名称|
|命名空间|与此形状相关联的命名空间。|当前命名空间|
|工具提示类型|如何定义工具提示 （固定的变量，或无）。 如果固定，然后的值`Fixed Tooltip Text`属性用作工具提示; 如果变量，然后在工具提示中定义自定义代码。|None|
|说明|与此元素相关联的非正式说明。|\<none>|
|初始高度|此形状，以英寸为单位的初始高度。|1|
|初始宽度|此形状，以英寸为单位的初始宽度。|1.5|
|作为属性公开的填充颜色<br /><br /> 公开的填充渐变模式<br /><br /> 作为属性公开轮廓颜色<br /><br /> 作为属性公开边框虚线线型<br /><br /> 公开为属性的边框粗细<br /><br /> 公开文本颜色|如果`True`，用户可以设置形状的规定的属性。 若要将此项设置，请右键单击形状定义，然后单击**公开添加**。|False|
|描述|用于记录生成的设计器中的说明。|\<none>|
|显示名称|将此形状的生成设计器中显示的名称。|\<none>|
|固定工具提示文本|用于固定工具提示文本。|\<none>|
|帮助关键字|用于索引此形状的 F1 帮助关键字。|\<none>|

## <a name="see-also"></a>请参阅

- [域特定语言工具术语表](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)