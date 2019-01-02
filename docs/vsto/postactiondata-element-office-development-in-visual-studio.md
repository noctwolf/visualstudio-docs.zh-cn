---
title: '&lt;postActionData&gt;元素 （Visual Studio 中的 Office 开发）'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- <postActionData> element
- application manifests [Office development in Visual Studio], <postActionData> element
- postActionData element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 58b085e35971fa557d946f3967af4db81b577fff
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/27/2018
ms.locfileid: "53804820"
---
# <a name="ltpostactiondatagt-element-office-development-in-visual-studio"></a>&lt;postActionData&gt;元素 （Visual Studio 中的 Office 开发）
  `postActionData` 命名空间的 `vstav3` 元素指定与任何部署后操作关联的数据，这些操作在 Office 解决方案安装后运行。

## <a name="syntax"></a>语法

```xml
<postActionData>
</postActionData>
```

## <a name="elements-and-attributes"></a>元素和属性
 `postActionData` 元素是可选的且位于 `vstav3` 命名空间中。 每个部署后操作的应用程序清单中只定义了一个 `postActionData` 元素。

 `postActions` 元素没有属性。

 `postActions` 无子元素。

## <a name="post-deployment-action-example"></a>部署后操作示例

### <a name="description"></a>描述
 下面的代码示例演示 Office 解决方案的应用程序清单中的 `postAction` 元素，该解决方案是使用 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]部署的。 此代码示例摘自[Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)。

### <a name="code"></a>代码

```xml
<vstav3:postActionData>
  data in any format
</vstav3:postActionData>
```

## <a name="see-also"></a>请参阅

- [Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)
- [Office 解决方案的部署清单](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce 应用程序清单](../deployment/clickonce-application-manifest.md)
